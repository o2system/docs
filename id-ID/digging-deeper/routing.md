
# Routing

Dalam membangun website, URL yang mudah diingat itu penting. Selain memudahkan user untuk mengingat alamat web, URL yang deskriptif juga sangat berpengaruh dalam SEO.


O2system menangani perihal URL ini dengan serius. Jika menggunakan PHP native, untuk membangun URL, biasanya dibangun dengan subfolder. Misalnya, kita memiliki website  blog dengan beberapa kategori di dalamnya dengan folder kategori di dalam sufolder tersebut. Contohnya bisa kurang lebih seperti ini folder yang akan di bangun

## HTTP Verbs

Untuk memahami penggunaan routing O2system, kita harus memahami HTTP Verb. Verb atau kata kerja dalam HTTP, menentukan jenis aksi yang akan dilakukan oleh request yang dilakukan.

Terdapat 5 jenis verb yang didukung O2system:

1. `GET` : Digunakan untuk meminta resource dari server.
2. `POST` : Digunakan untuk menyimpan resource ke server.
3. `PUT` : Digunakan untuk melakukan update resource di server.
4. `PATCH` : Digunakan untuk melakukan update resource di server.
5. `DELETE` : Digunakan untuk menghapus resource di server.

PUT dan PATCH sering digunakan untuk hal yang sama (meng-update). Perbedaan keduanya,
secara teoritis PUT bekerja dengan menimpa (replace) resource dengan resource yang baru.

sintaks dasar dari routing O2system menggunakan HTTP Verb seperti berikut ini.

```php
$addresses->get('...', '...');
$addresses->post('...', '...');
$addresses->put('...', '...');
$addresses->delete('...', '...');
$addresses->option('...', '...');
$addresses->trace('...', '...');
```
Misalnya untuk membuat URL ke halaman kontak, kita bisa menambah baris berikut di file
`app/Config/Addresses.php`:


```php
use O2System\Kernel\Http\Router\Addresses;

$addresses = new Addresses();

$addresses->get('kontak', function() {
return '<h1>halaman kontak</h1>';
});
```

## Perlindungan dari CSRF



```html
<form action="<?=base_url('login/authenticate');?>" method="post">
<input type="hidden" name="csrf-token" value="{{ $csrfToken }}">
</form>
```

## Redirect Routes

