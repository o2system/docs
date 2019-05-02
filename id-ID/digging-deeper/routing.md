
# Routing

Routing pada O2system sangat flexible. O2system secara default akan membuat sebuah route standar dengan menggunakan nama class Controller dan method dan variabel.

Segmen url O2system biasanya seperti berikut ini.

```
example.com/class/method/id
```

Kadang, Anda ingin memetakan beberapa kasus, Anda mungkin ingin memetakan ulang hubungan ataira class atau method yang berbeda dan dapat di panggil sesu dengan alamat url yang di inginkan.

```
example.com/product/1/
example.com/product/2/
example.com/product/3/
example.com/product/4/
```

## Konfigurasi Routing

Konfigurasi routing O2system bisa di edit di app/Config/Addressess.php. Pada file ini Anda dapat menentukan kriteria perutean aplikasi web Anda sediri. Route bisa di buat menggunakan wildcard eatau ekspresi reguler.

```php
// Example Route To Default Controller
$addresses->any(
    '/',
    function () {
        return new \App\Controllers\Hello();
    }
);
```


## HTTP Verbs

Untuk memahami penggunaan routing O2system, kita harus memahami HTTP Verb. Verb atau kata kerja dalam HTTP, menentukan jenis aksi yang akan dilakukan oleh request yang dilakukan.

Terdapat 5 jenis verb yang didukung O2system:

1. `GET` : Digunakan untuk meminta resource dari server.
2. `POST` : Digunakan untuk menyimpan resource ke server.
3. `PUT` : Digunakan untuk melakukan update resource di server.
4. `PATCH` : Digunakan untuk melakukan update resource di server.
5. `DELETE` : Digunakan untuk menghapus resource di server.

**PUT** dan **PATCH** sering digunakan untuk hal yang sama (meng-update). Perbedaan keduanya,
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

