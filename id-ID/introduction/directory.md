
# Direktori

Setiap project yang menggunakan O2System Framework memiliki 5 struktur direktori dasar pada root-nya, yang terdiri dari:



<ul class="file-tree">
    <li>
        <a href="#">app</a>
        <ul>
            <li>
                <a href="#">Config</a>
                <ul>
                    <li>
                        <a href="#"> AccessControl.php</a>
                    </li>
                    <li>
                        <a href="#"> Cache.php</a>
                    </li>
                    <li>
                        <a href="#"> Database.php</a>
                    </li>
                    <li>
                        <a href="#"> Email.php</a>
                    </li>
                    <li>
                        <a href="#"> Hooks.php</a>
                    </li>
                    <li>
                        <a href="#"> Manifest.php</a>
                    </li>
                    <li>
                        <a href="#"> Parser.php</a>
                    </li>
                    <li>
                        <a href="#"> Session.php</a>
                    </li>
                    <li>
                       <a href="#"> Addresses.php</a>
                   </li>
                   <li>
                       <a href="#"> Config.php</a>
                   </li>
                   <li>
                       <a href="#"> Helpers.php</a>
                   </li>
                   <li>
                       <a href="#"> Image.php</a>
                   </li>
                   <li>
                       <a href="#"> Models.php</a>
                   </li>
                   <li>
                       <a href="#"> Services.php</a>
                   </li>
                   <li>
                       <a href="#"> View.php</a>
                   </li>
               </ul>
           </li>
           <li>
            <a href="#">Controllers</a>
            <ul>
             <li>
                 <a href="#">.gitkeep</a>
             </li>
         </ul>
     </li>
     <li>
        <a href="#">Helpers</a>
        <ul>
         <li>
             <a href="#">.gitkeep</a>
         </li>
     </ul>
 </li>
 <li>
    <a href="#">Http</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Languages</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Libraries</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Models</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Modules</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Presenters</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">Widgets</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">app.json</a>
</li>
</ul>
</li>
<li>
    <a href="#">cache</a>
    <ul>
        <li>
            <a href="#">.gitkeep</a>
        </li>
    </ul>
</li>
<li>
    <a href="#">database</a>
    <ul>
        <li>
            <a href="#">Factory</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">Migrations</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">Seeds</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
    </ul>
</li>
<li>
    <a href="#">node_modules</a>
    <ul>
    </ul>
</li>
<li>
    <a href="#">public</a>
    <ul></ul>
</li>
<li>
    <a href="#">resources</a>
    <ul>
        <li>
            <a href="#">Config</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">Pages</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">Themes</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">views</a>
            <ul>
                <li>
                    <a href="#">.gitkeep</a>
                </li>
            </ul>
        </li>
    </ul>
</li>
<li>
    <a href="#">storage</a>
    <ul></ul>
</li>
<li>
    <a href="#">vendor</a>
    <ul></ul>
</li>
<li>
    <a href="#">cli.php</a>
</li>
<li>
    <a href="#">composer.json</a>
</li>
<li>
    <a href="#">LICENSE</a>
</li>
<li>
    <a href="#">o2system</a>
</li>
<li>
    <a href="#">package.json</a>
</li>
<li>
    <a href="#">package-lock.json</a>
</li>
<li>
    <a href="#">README.md</a>
</li>
<li>
    <a href="#">server.php</a>
</li>
</ul>


Masing-masing direktori tersebut memiliki peruntukannya masing-masing.

## Direktori App

Direktori aplikasi berisi semua source-code aplikasi anda yang tersusun rapi sesuai dengan peruntukkannya masing-masing. Secara default, direktori ini berada dalam namespace App dan di-autoload oleh Composer dan O2System Framework autoloader menggunakan standar autoloading PSR-4.

> Hampir seluruh file class-class php pada folder app dapat digenerate menggunakan O2System Console Commands. Untuk mempelajari perintah-perintahnya, jalankan perintah:

```sh
php o2system make --help
```

Seperti yang terlihat pada gambar diatas, struktur pada direktori app memiliki beberapa sub-direktori. Beberapa diantaranya merupakan sub-direktori yang memiliki fungsi penting dan tidak dapat anda gantikan nama sub-direktori tersebut dengan nama lain. Walaupun demikian anda tetap dapat menambahkan sub-direktori baru dengan nama lain sesuai dengan preferensi masing-masing namun harus tetap mematuhi standar penulisan nama direktori PSR-4.


###  Direktori Config

Tempat menyimpan semua file-file konfigurasi aplikasi anda. File Config diharuskan ber-format file PHP, yang berisikan variable bertipe array atau bertipe object dari class `O2System\Kernel\DataStructures\Config`, berlaku untuk turunannya. Penamaan nama variable harus ber-format camelcase dari nama filename Config tersebut, sedangkan untuk penulisan nama filename harus berstandar PSR-4 yaitu dengan format penulisan StudlyCase.

```php
<?php
/**
 * $yourConfig
 *
 * Configuration example.
 *
 * @var array
 */
$yourConfig = [
    'key' => 'value'
];
// ------------------------------------------------------------------------

/**
 * $yourConfig
 *
 * Configuration example.
 *
 * @var \O2System\Kernel\DataStructures\Config
 */
$yourConfig = new \O2System\Kernel\DataStructures\Config([
    'key' => 'value'
]);
```

> Script diatas harus disimpan dengan filename 
`app/Config/YourConfig.php`


###  Direktori Controllers/Commanders

Tempat menyimpan semua file-file Controller/Commander class aplikasi anda. File Controller/Commander class diharuskan ber-format file PHP, yang berisikan script PHP class Controller. Penamaan class dan filename harus berstandar PSR-4 yaitu dengan format penulisan StudlyCase dan harus disertai dengan namespace.

```php
<?php
namespace App\Controllers;

use O2System\Framework\Http\Controller;

/**
 * Class HelloWorld
 *
 * HelloWorld controller class example.
 *
 * @package App\Controllers
 */
class HelloWorld extends Controller
{
    /**
     * HelloWorld::index
     *
     * HelloWorld index.
     */
    public function index()
    {
        // write your business-logic here.
    }
}
```

> Script diatas harus disimpan dengan filename `app/Controllers/HelloWorld.php`

###  Direktori Helpers 

Tempat menyimpan semua file-file Helper aplikasi anda. File Helper diharuskan ber-format file PHP, yang berisikan script fungsi-fungsi yang anda tulis khusus untuk aplikasi anda. Setiap penulisan fungsi disarankan seperti sample dibawah ini dan harus berstandar PSR-1 dan PSR-2. Sedangkan untuk penulisan nama filename harus berstandar PSR-4 yaitu dengan format penulisan StudlyCase.

```php
<?php
/**
 * Your Helper Collection
 *
 * Example helper collection.
 */
// ------------------------------------------------------------------------

if ( ! function_exists('my_function')) {
    /**
     * my_function
     *
     * Example helper function.
     *
     * @param array $parameter_1 First parameter of my function.
     *
     * @return mixed
     */
    function my_function(array $parameter_1 = [])
    {
// write your function-logic here.
    }
}

// ------------------------------------------------------------------------
```

> Script diatas harus disimpan dengan nama filename `app/Helpers/YourHelper.php`

###  Direktori Languages 

Tempat menyimpan semua file-file Language (bahasa) aplikasi anda. File-file tersebut diharuskan ber-format file INI. Dalam direktori Languages anda dapat mengelompokkan kembali setiap file-file bahasa ke dalam sub-direktori yang diberi nama sesuai dengan standar kode bahasa atau apabila anda merasa tidak perlu mengelompokkannya ke dalam sub-direktori anda dapat menamakan file Language dengan filename yang ditambahkan suffix (akhiran) kode bahasa.

```ini
;; Example INI Language file en-US
HELLO_WORLD = "Hello World"
```

> Disimpan didalam sub-direktori berdasarkan bahasa
`app/Languages/en-US/nama-file.ini`

> Disimpan dengan tambahan suffix bahasa
`app/Languages/nama-file_en-US.ini`

```ini
;; Example INI Language file id-ID
HELLO_WORLD = "Halo Dunia"
```

> Disimpan didalam sub-direktori berdasarkan bahasa
app/Languages/id-ID/nama-file.ini

> Disimpan dengan tambahan suffix bahasa
app/Languages/nama-file_id-ID.ini

Hal terpenting pertama dalam penulisan file Language adalah language key parameter harus dituliskan dengan format CAPSLOCK dan menggunakan underscore `_` sebagai pemisah kata. Hal terpenting kedua yaitu language key parameter pada setiap bahasa tidak boleh berubah seperti pada contoh diatas.

> Tips and Trick
Jika anda menuliskan nama filename sama dengan salah satu controller/commander class maka secara otomatis file language tersebut akan diload oleh O2System Framework ketika controller/commander tersebut diakses.

###  Direktori Libraries 

Tempat menyimpan semua file-file Library class aplikasi anda. File Library class diharuskan ber-format file PHP yang berisikan script PHP class. Penamaan class dan filename harus berstandar PSR-4 yaitu dengan format penulisan StudlyCase dan harus disertai dengan namespace.

```php
<?php
namespace App\Libraries;

/**
 * Class MyClass
 *
 * Library class example.
 *
 * @package App\Libraries
 */
class MyClass
{
    /**
     * MyClass::__construct
     *
     * MyClass constructor.
     */
    public function __construct()
    {
        // write your logic here
    }
}
```

> Script diatas harus disimpan dengan nama filename `app/Libraries/MyClass.php`

###  Direktori Models

Tempat menyimpan semua file-file Model class aplikasi anda. File Model class diharuskan ber-format file PHP yang berisikan script PHP class. Penamaan class dan filename harus berstandar PSR-4 yaitu dengan format penulisan StudlyCase dan harus disertai dengan namespace.

```php
<?php
namespace App\Models;

use O2System\Framework\Models\Sql\Model;

/**
 * Class HelloWorld
 *
 * HelloWorld model class example.
 *
 * @package App\Models
 */
class HelloWorld extends Model
{
    /**
     * HelloWorld::$table
     *
     * HelloWorld database table name
     *
     * @var string
     */
    public $table = 'hello_world';
}
```

> Script diatas harus disimpan dengan nama filename `app/Models/HelloWorld.php`

> Tips and Trick
> Jika anda menuliskan nama filename sama dengan salah satu controller class maka secara otomatis file Model class tersebut akan diload oleh O2System Framework ketika controller tersebut diakses.

###  Directory Modules

Direktori Modules berisi semua aplikasi web yang ingin di buat modular. direktor ini berisi seperti pada folder app seperti config, controller, helpers, http, language, language dan app.json 

###  Direktori Presenter

###  Directory Widgets

##  Direktori Cache

Direktori cache berfungsi sebagai tempat penyimpanan dari semua file cache dari template parser yang dikompilasi, sesi berbasis file, registri berbasis file, cache manipulasi gambar, file logging dan cache lainnya yang dihasilkan oleh aplikasi dan framework. Setiap file cache disimpan dalam folder yang dinamai sesuai dengan namanya.

##  Director Database

### Migration

Direktori ini berisikan file-file migrations yang digenerate oleh O2Sytem pada saat kita menjalankan perintah php o2system make:migration. fitur migration sendiri sangat berguna untuk melakukan perubahan pada database baik itu penambahan tabel, penambahan kolom, menghapus kolom, menghapus tabel serta melakukan roll-back setiap perubahan database yang kita buat. Fitur migration ini akan sangat terasa manfaatnya terutama pada saat kita mengerjakan sebuah project di dalam sebuah tim dan banyak struktur database yang berubah seiring perkembangan project. 

### Seeds

Direktori ini berisikan file-file database seeds yang digenerate oleh O2System pada saat kita menjalankan perintah php o2system make:seeder. fitur seeding di O2system sendiri sangat berguna apabila kita ingin melakukan inisialisasi data (data awalan) pada table yang kita buat. 

##  Direktori Public

Direktori publik berfungsi sebagai root document dari web server anda, di mana semua file yang dapat diakses oleh publik akan ditempatkan di direktori ini seperti file javascript, css, gambar dan asset lainnya. Index.php yang berfungsi sebagai front-controller dari permintaan http aplikasi anda terletak di direktori ini. Asset dan tema yang digunakan oleh aplikasi Anda juga terletak di dalam direktori ini.

##  Directory Resources

Direktori ini memiliki tiga buah sub direktori yaitu config, themes, dan views. Berikut ini adalah penjelas singkat terkait fungsi dari masing-masing sub direktori tersebut:

### Config
Folder Config berisi file konfigurasi O2System untuk mengkompilasi  file asset yang berupa sass, dan js(es6) yang ada di folder themes. konfigurasi tersebut menggunakan [nodejs](https://nodejs.org/en/download/)

### Themes

Folder disini merupakan sekumpulan file assets berupa, sass, js, images dll yang akan di kompile sesui yang ada di konfigurasi di folder config.


### views

Direktori ini digunakan untuk menyimpan seluruh file html / template yang kita buat.


##  Direktori Storage

Direktori storage berfungsi sebagai tempat penyimpanan raw-files atau file-file yang di-upload dari aplikasi anda.

##  Direktori Vendor

Direktori vendor berisi library-library dari Composer Dependencies yang diperlukan oleh project aplikasi anda, termasuk didalamnya library-library dari O2System Framework.