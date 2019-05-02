# Bekerja dengan Model

Dalam framework yang menggunakan pola desain MVC, model merupakan komponen yang merepresentasikan modeling object data yang digunakan pada aplikasi.

Mari kita mulai membuat sebuah model pada O2System Framework. Sebagai contoh kita akan membuat model untuk menampilkan artikel dari database yang paling populer digunakan yaitu MySQL.

## Mengubah Konfigurasi

Untuk mulai bekerja dengan database anda harus melakukan konfigurasi database terlebih dahulu. Konfigurasi database tersimpan pada directory Config dari aplikasi anda.

Bukalah file konfigurasi Database.php anda akan melihat source code seperti dibawah ini. Lakukanlah perubahan sesuai dengan konfigurasi MySQL anda.

```php
<?php

$database[ 'default' ] = [
    'driver'       => 'mysql',
    'dsn'          => '',
    'hostname'     => 'localhost',
    'port'         => 3306,
    'username'     => 'root',
    'password'     => 'mysql',
    'database'     => 'o2system_tutorial',
    'charset'      => 'utf8',
    'collate'      => 'utf8_general_ci',
    'tablePrefix'  => '',
    'strictOn'     => false,
    'encrypt'      => false,
    'compress'     => false,
    'buffered'     => false,
    'persistent'   => true,
    'transEnable' => false,
    'cacheEnable' => false,
    'debugEnable' => true,
];
```

## Membuat Table Database

Buatlah sebuah table database dengan perintah MySQL dibawah ini:

```sql
CREATE TABLE `articles` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `title` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `content` text COLLATE utf8_unicode_ci DEFAULT NULL,
  `record_status` enum('DELETE','ARCHIVE','DRAFT','UNPUBLISH','PUBLISH') COLLATE utf8_unicode_ci DEFAULT 'PUBLISH',
  `record_create_timestamp` datetime DEFAULT NULL,
  `record_create_user` int(10) unsigned DEFAULT NULL,
  `record_update_timestamp` timestamp NULL DEFAULT NULL ON UPDATE current_timestamp(),
  `record_update_user` int(10) unsigned DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci ROW_FORMAT=COMPACT;
```

Di O2System Framework modeling anda akan diperkenalkan dengan sebuah konsep skema table database baru dimana pada setiap table akan terdapat kolom-kolom berawalan record yang selanjutnya akan disebut sebagai record set.

```sql
INSERT INTO `o2system_tutorial`.`articles`(`id`, `title`, `content`, `record_status`, `record_create_timestamp`, `record_create_user`, `record_update_timestamp`, `record_update_user`) VALUES (1, 'My First Article', 'This is my first article.', 'PUBLISH', '2018-10-08 09:06:21', NULL, '2018-10-08 09:06:21', NULL);
INSERT INTO `o2system_tutorial`.`articles`(`id`, `title`, `content`, `record_status`, `record_create_timestamp`, `record_create_user`, `record_update_timestamp`, `record_update_user`) VALUES (2, 'My Second Article', 'This is my second article.', 'PUBLISH', '2018-10-08 09:08:31', NULL, '2018-10-08 09:08:31', NULL);
```

## Membuat Model

Buatlah sebuah file Model berekstensi php dan simpanlah pada directory Model, berisikan source code seperti pada contoh dibawah ini:

```php
<?php
namespace App\Models;
​
use O2System\Framework\Models\Sql\Model;
​
/**
* Class Articles
*
* @package App\Models
*/
class Articles extends Model
{
    public $table = 'articles';
}
```

## Membuat Controller

Buatlah sebuah file Controller baru, berisikan source code seperti pada contoh dibawah ini:

```php
<?php
namespace App\Controllers;
​
use O2System\Framework\Http\Controller;
​
/**
* Class Articles
*
* @package App\Controllers
*/
class Articles extends Controller
{
    public function index() 
    {
        print_out( $this->model->allWithPaging() );
    }
}
```

Pada langkah pembuatan Controller kali ini anda akan berkenalan dengan 4 fitur   pintar dari O2System Framework yaitu:

### Debugger Print Out

Fungsi print_out merupakan salah satu fitur debugging dari Atom Gear pada O2System Framework. Fitur ini sangat membantu sekali, karena secara pintar O2System akan mengumpulkan informasi-informasi penting untuk membantu kita melakukan proses debugging. 

Sebagai contoh ilustrasi kita perlu melihat bagaimana struktur object model data articles yang telah kita buat pada langkah-langkah sebelumnya. Cobalah akses melalui browser anda ke alamat URL

```
http://localhost:8000/articles
```

Anda akan melihat tampilan debugger print_out yang dilengkapi dengan beberapa informasi penting salah satunya adalah debug backtrace, yang akan selalu memberitahu kepada anda dari mana fungsi print_out ini dijalankan serta perjalanan prosesnya.

### Identical Model Autoloading

Identical Model Autoloading salah satu fitur dari O2System Framework dimana O2System secara pintar akan mencari Model yang memiliki nama class yang sama dengan nama class Controller yang diakses pada namespace Models. Jadi anda tidak perlu repot memanggilnya karena secara pintar O2System telah menyediakannya sebagai property pada class Controller yang anda akses dengan property "model". Pada contoh diatas anda telah mempergunakannya yaitu:

```php
$this->model
```

### Built-in Finder-Trait

Class model yang anda buat di langkah sebelumnya merupakan turunan dari class SQL Model pada O2System Framework. Didalamnya telah terdapat Finder-Trait yang merupakan salah satu modeling reusable-code pada O2System Framework, berfungsi untuk menyediakan metode-metode pencarian pada model. Pada contoh diatas anda telah mempergunakan salah satunya yaitu:

```php
$this->model->allWithPaging();
```

Perhatikan source code model yang anda miliki, didalamnya hanya terdapat pendefinisian property table dengan nilai articles yang merujuk kepada nama table articles pada database. Secara pintar O2System Framework akan melakukan kalkulasi pembangunan SQL Statement melalui fitur Query Builder yang merupakan salah satu fitur dari Atom Database, lalu mengeksekusinya sebagai perintah MySQL dan menyediakan hasilnya kepada anda dalam bentuk Data Object Result.

### Data Object Result

Data Object Result merupakan bentuk Modeling Data Object pintar berfitur unik yang akan sangat mempercepat kinerja anda. Beberapa fitur diantaranya adalah:

1. Object Relation Mapping (ORM)
2. SPL Array Iterator
3. JsonSerializeable Interface
4. User Interface Pagination Component

Masih banyak lagi fitur-fitur yang tertanam didalamnya. Anda dapat mempelajarinya pada bagian pendalaman ORM.

### Membuat View

Buatlah sebuah file View baru, berisikan source code seperti pada contoh dibawah ini:


```php
<h1>Articles</h1>
{{ if($articles) }}
    {{ foreach($articles as $article) }}
        <h2>{{ $article->title }}</h2>
        <p>{{ $article->content }}</p>
        <hr>
    {{ /foreach }}
    {{ $articles->pagination() }}
{{ /if }}
```

Pada langkah pembuatan view sebelumnya kita diajarkan untuk menggunakan fungsi echo bahasa programming PHP. Namun pada langkah pembuatan view kali ini anda diperkenalkan dengan salah satu fitur template parser pada O2System Framework yaitu Noodle Template Parser. Noodle Template Parser memiliki kesederhanaan bahasa templating karena memiliki banyak kesamaan perintah dengan bahasa programming PHP. 

## Melakukan Kombinasi MVC

Setelah kita selesai membuat Controller, Model dan View langkah selanjutnya adalah memadukannya sesuai dengan pola MVC melalui Controller.

Bukalah kembali file Controller Articles yang telah kita buat tadi lakukan perubahan dengan mengganti line source code kita yang berisikan fungsi print_out tadi seperti source code dibawah ini:

```php
<?php
namespace App\Controllers;
​
use O2System\Framework\Http\Controller;
​
/**
* Class Articles
*
* @package App\Controllers
*/
class Articles extends Controller
{
    public function index() 
    {
        $this->load->view('articles', [
            'articles' => $this->model->allWithPaging();
        ]);
    }
}
```
Untuk penggunaan lebih lanjut anda dapat membacanya pada bagian pendalaman [Model]().