# Bekerja dengan Controller

Dalam framework yang menggunakan pola desain MVC, controller merupakan komponen utama yang berperan sebagai pemroses permintaan. Anda bisa saja membuat aplikasi berpola MVC tanpa menggunakan model atau view namun tidak mungkin tanpa menggunakan komponen controller.

Mari kita mulai membuat sebuah controller pada O2System Framework. Sebagai contoh kita akan membuat halaman Hello World dengan menggunakan controller.

## Membuat Controller

Buatlah sebuah file Controller berekstensi php dan simpanlah pada directory Controller, berisikan kode seperti pada contoh dibawah ini:

```php
<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
* Class HelloWorld
*
* @package App\Controllers
*/
class HelloWorld extends Controller
{
}
```

## Membuat Metode

Tambahkanlah kode seperti dibawah ini pada file controller yang telah anda buat pada langkah sebelumnya, metode pada controller mereprentasikan aksi yang akan dieksekusi.

```php

<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
* Class HelloWorld
*
* @package App\Controllers
*/
class HelloWorld extends Controller
{
   /**
    * HelloWorld::index
    */
    public function index()
    {
        
    } 
}
```

## Membuat View

Buatlah sebuah file View bereksentsi phtml dan simpanlah pada directory Views, berisikan kode seperti pada contoh dibawah ini:

```php
<h1>Hello World!</h1>
```

## Memanggil View

Setelah anda membuat file View, mari kita kembali kepada file Controller yang telah anda buat pada langkah pertama. Tambahkanlah perintah pemanggilan view seperti kode dibawah ini pada metode controller.

```php
<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
* Class HelloWorld
*
* @package App\Controllers
*/
class HelloWorld extends Controller
{
   /**
    * HelloWorld::index
    */
    public function index()
    {
        $this->load->view('hello-world');
    } 
}
```

Alternatif perintah untuk melakukan pemanggilan view pada controller yang anda buat adalah dengan perintah seperti dibawah ini.

```php
<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
* Class HelloWorld
*
* @package App\Controllers
*/
class HelloWorld extends Controller
{
   /**
    * HelloWorld::index
    */
    public function index()
    {
        view('hello-world');
    } 
}
```

> Pilihlah gaya bahasa penulisan kode yang anda sukai dan terapkan selanjutnya sebagai standarisasi gaya penulisan kode anda.


## Mengirim Data

Pada langkah-langkah sebelumnya kita telah mempelajari bagaimana cara membuat controller, metode controller dan melakukan perintah untuk memanggil view pada controller. Langkah selanjutnya yang akan kita pelajari adalah bagaimana melakukan pengiriman data atau variable ke view melalui controller.

```php
<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
* Class HelloWorld
*
* @package App\Controllers
*/
class HelloWorld extends Controller
{
   /**
    * HelloWorld::index
    */
    public function index()
    {
        $this->load->view('hello-world', [
            'name' => 'Steeven Andrian'
        ]);
    } 
}
```

Untuk memanggil data tersebut pada file view anda ubahlah file view yang telah anda buat tadi pada langkah ke 3, seperti kode dibawah ini:

```php
<h1>
    Hello World!
    <small class="text-muted">
        My name is <?php echo $name; ?>
    </small>
</h1>
```

## Mengakses Controller

Anda dapat mengakses halaman dengan controller ini melalui browser anda dengan mengetikkan alamat URL seperti dibawah ini:

```
http://localhost:8000/hello-world
```

Perhatikan format penulisan segmentasi url about-us diatas yang berformat dash. Format ini merupakan cara penulisan alamat segmentasi url yang paling dianjurkan karena bersifat Search Engine Friendly (SEF) URL.

Khusus untuk metode index pada controller anda tidak perlu menuliskannya pada alamat URL anda.
Untuk penggunaan lebih lanjut anda dapat membacanya pada bagian pendalaman Controller.