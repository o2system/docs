# Uploader

File Uploading Class O2System memungkinkan file untuk diunggah. Anda dapat mengatur berbagai preferensi, membatasi jenis dan ukuran file.

## Proses

Mengunggah file melibatkan proses umum berikut:

- For unggahan ditampilkan, memungkinkan pengguna untuk memilih file dan mengunggahnya.
- Ketika form  dikirimkan, file diunggah ke tujuan yang Anda tentukan.
- Pada saat file di proses, file divalidasi untuk memastikan bahwa file tersebut diizinkan untuk diunggah berdasarkan preferensi yang Anda tetapkan.
- Setelah diunggah, pengguna akan melihat pesan sukses.

Berikut ini merupakan tutorial singkat bagaimana mengunggah file ke dalam applikasi web yang di buat.


### Membuat sebuah form

Buatlah sebuah form.phtml pada direktori resources/view.

```php
<html>
<head>
<title>Upload Form</title>
</head>
<body>

<?php if (null !== ($message = $session->getFlash('success'))): ?>
                        
<?php echo $language->getLine('ALERT_SUCCESS_HEADING'); ?>
<?php echo $message; ?>
<?php elseif (null !== ($message = $session->getFlash('danger'))): ?>
<?php echo $language->getLine('ALERT_DANGER_HEADING'); ?>
<?php echo $message; ?>
<?php endif; ?>

<form method="post" action="<?php echo base_url('upload/form'); ?>" enctype="multipart/form-data">
<input type="file" name="file" size="20" />
<input type="submit" value="upload" />
</form>

</body>
</html>
```

Form Unggahan file memerlukan atribut `enctype="multipart/form-data"`, sehingga helper membuat sintaks yang tepat untuk Anda. Anda juga akan melihat sebuah variabel `$message`. Variabel tersebut digunakan untuk  menampilkan pesan kesalahan jika pengguna melakukan kesalahan.


### Controller

Buatlah sebuah controller upload form pada direktori `app/Controllers`.

```php
<?php

namespace App\Controllers;


use App\Http\Controller;
use O2System\Filesystem\Handlers\Uploader;
/**
 * Class Upload
 * @package App\Models\Controllers
 */
class Upload extends Controller
{
    public function form()
    {
        $this->load->view( 'form');
    }


    public function imageUpload()
    {
        
        if (input()->files('file')) {
            $imagePath = PATH_STORAGE . 'images/files';
            if (!file_exists($imagePath)) {
                mkdir($imagePath, 0777, true);
            }
            $upload = new Uploader();
            $upload->setPath($imagePath);
            $upload->process('file');

            if ($upload->getErrors()) {
                $errors = new Unordered();

                foreach ($upload->getErrors() as $code => $error) {
                    $errors->createList($error);
                }

                session()->setFlash('danger', $errors);

                redirect_url('form');
            }
        }
    }
}
```

### Direktori Upload

Pada fungsi di controller di atas. Folder akan di buat jika belum ada dengan pengaturan permisi 0777. Untuk mengecek apakah gambar telah terupload dengan baik ke server bisa di cek dengan mengakses alamat url secara langsung foldernya.

```
example.com/images/files/
```