# Controller

Controller merupakan class PHP yang memegang peranan penting dalam aplikasi karena menentukan bagaimana sebuah HTTP request dari user ditangani. Controller dapat memberikan lebih dari satu tindakan sebagai bentuk dari proses request tersebut yang kemudian harus disertai dengan tanggapan dari proses request tersebut.

Controller bertanggung jawab untuk mengendalikan logika dari aplikasi (business-logic) dan bertindak sebagai koordinator antara Model, Presenter dan View. Controller menerima request dari pengguna melalui View yang kemudian data permintaan tersebut diproses dengan bantuan Model lalu mempresentasikannya kembali ke View dengan bantuan Presenter.

Dalam mengembangkan aplikasi dengan Design Pattern HMVC, controller berperan untuk mengarahkan setiap request ke aplikasi. Controller umumnya digunakan untuk menjawab request yang dikirim ke route, yang selanjutnya akan diarahkan ke model yang diperlukan.

Dengan pemahaman ini, sebaiknya sebuah controller emang memiliki sedikit kode. Sementara model memiliki banyak kode, karena di model-lah business logic dari aplikasi akan berjalan. Teknik sedikit code di controller dan banyak kode di model ini biasa dikenal dengan istilah thick model, thin controller. Dan ini merupakan best practices yang bisa kita jadikan pegangan selama koding.

## Membuat sebuah Controller

Untuk membuat sebuah controller di O2System cukup mudah hanya dengan membuat sebuah class di folder `app/Controller`. nama controller sebaiknya di smaakan dnegan model yang di buat.

```php
<?php

namespace App\Controllers;

use App\Http\Controller;
class Post extends Controller
{
    public function index()
    {
        return 'hello World';
    }
}
```
apabila udah selesai silahkan dicek di browser dengan kesayangan anda dengan mengerikan `php o2system serve`

## Directory Location

Seluruh file Controller harus ditempatkan di dalam direktori khusus dengan nama direktor Controllers. Direktori Controllers dapat ditempatkan pada direktori utama aplikasi anda ataupun oleh module-module dari aplikasi anda.

## Available Controllers

Berikut ini adalah daftar file-file Controller yang secara default sudah tersedia:

- **Error Controller**

    Controller ini secara default diperuntukkan untuk memberikan respon error message berdasarkan kode.

- **Images Controller**

    Controller ini secara default diperuntukkan untuk mengakses file-file image dalam direktori storage images dan sekaligus sebagai penyedia *service image manipulation on-the-fly*.
    
- **Pages Controller**
    
    Controller ini secara default diperuntukkan untuk mengakses file-file static page dalam direktori Pages.
    
- **Restful Controller**
    
    Controller ini secara default adalah Base Controller apabila anda ingin membangun *restful web service*.
    
- **Storage Controller**
    
    Controller ini secara default diperuntukkan untuk mengakses file-file yang berada di dalam direktori storage dan sekaligus sebagai penyedia service file download.
    
- **Websocket Controller**
    
    Controller ini secara default adalah Base Controller apabila anda ingin membangun *websocket web service*.
    

## Controller Methods

Secara default ada dua (2) metode penting yang secara default selalu dimuat oleh sistem router dari O2System Framework, yaitu:

1. Index Method

    Index method akan dipanggil jika router dua (2) kondisi dibawah ini memenuhi syarat:
    
    - URI segment method kosong
    
        Setelah router berhasil menemukan Controller yang diminta, apabila URI selanjutnya kosong maka secara otomatis Controller Method yang akan dipanggil adalah index method.
        
    - URI segment method terdefinisi sebagai parameter untuk index
        
        Setelah router berhasil menemukan Controller yang diminta, apabila router tidak berhasil menemukan Controller Method yang sesuai dengan yang diminta pada segment method namun Controller memiliki index method yang menerima parameter. Maka router akan memanggil index method yang selanjutnya secara otomatis akan mendefinisikan dan mengubah segment-segment lain menjadi parameter untuk index method tersebut.
        
        `ControllerClassName::index(firstParam, secondParam)`
    
2. Route Method
    
    Router method merupakan sebuah metode yang berfungsi untuk melakukan internal routing pada Controller yang berperan sebagai pengambil alih tugas sistem router melalui Controller. Parameter pertama pada Controller::route() method merupakan segment method yang sebelumnya akan dipanggil melalui sistem router, sedangkan segment-segment lainnya akan diubah menjadi argument dan didefinisikan sebagai parameter kedua dari Controller::route() method.
        
    `ControllerClassName::route(method, args)`

## Create a Controller

Cara termudah membuat controller pertama kali adalah melalui O2System Console, dengan perintah:

```bash
php o2system make:controller --name=ControllerClassName
```
Option-option yang tersedia lainnya adalah:


| Option  | Shortcut  |Terms    |Description|
|---------|-----------|---------|-----------|
|--name   |-n|required|Menentukan nama dari Controller
|--path   |-p|optional|Menentukan penempatan di direktori lain, selain direktori default, yaitu `app/Controllers/`
|--namespace|-ns|optional|Menentukan namespace lain, selain namespace default, yaitu `App\Controllers`


Berikut adalah contoh dasar dari penulisan source code sebuah Controller:

```php
namespace App\Controllers; 

use O2System\Framework\Http\Controller;

/**
 * Class ControllerClassName
 *
 * @package App\Controllers
 */
class ControllerClassName extends Controller
{
    /**
     * ControllerClassName::__construct
     */
    public function __construct()
    {
        parent::__construct();
    }
    
    /**
     * ControllerClassName::index
     */
    public function index()
    {
        // TODO: Change the autogenerated stub
    }
}
```

## Konfigurasi

Secara default hasil url yang di hasilkan adalah sesui dengan nama controller yang di buat  seprti pada control diatas maka hasilnya adalah `localhost:8000/post`. Jika ingin membuat custom url yang di inginkan maka kita tinggal mengedit file `app/config/addresses.php` 

```php
<?php
use O2System\Kernel\Http\Router\Addresses;

$addresses = new Addresses();

$addresses->get(
    'blog',
    function () {
        return new \App\Controllers\Post();
    }
);
```

Pada konfigurasi di atas maka konfigurasi route `localhost:8000/post` berubah menjadi `localhost:8000/blog`
