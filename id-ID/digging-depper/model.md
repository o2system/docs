# Models

Model merupakan sebuah PHP class yang berperan sebagai sebuah rancangan dari data yang digunakan dalam aplikasi. Model dirancang untuk bekerja dengan informasi dari database.

## Directory Location

Seluruh file Model harus ditempatkan di dalam direktori khusus dengan nama direktor Models. Direktori Models dapat ditempatkan pada direktori utama aplikasi anda ataupun oleh module-module dari aplikasi anda.

## Membuat Model

Cara termudah membuat model pertama kali adalah melalui O2System Console, dengan perintah:

```bash
php o2system make:model --name=ModelClassName
```

Option-option yang tersedia lainnya adalah:


|Option|Shortcut|Terms|Description|
|------|--------|-----|-----------|
|--name|-n|required|Menentukan nama dari Model
|--path|-p|optional|Menentukan penempatan di direktori lain, selain direktori default, yaitu `app/Models/`
|--namespace|-ns|optional|Menentukan namespace lain, selain namespace default, yaitu `App\Models`


Berikut adalah contoh dasar dari penulisan source code sebuah Model:

```php
namespace App\Models;

use O2System\Framework\Models\Sql\Model;

/**
 * Class ModelClassName
 *
 * @package App\Models
 */
class ModelClassName extends Model
{
    /**
     * ModelClassName::__construct
     */
    public function __construct()
    {
        parent::__construct();
    }
}
```

Di O2System Framework anda akan diperkenalkan kepada istilah baru yaitu sub-model. Sub-model merupakan salah satu bentuk dari perluasan model yang akan di-load apabila sub-model tersebut dibutuhkan. Untuk membuat sub-model ada beberapa perbedaan yang harus diperhatikan, yaitu

- Lokasi Sub-Model

    Sub-model harus disimpan di dalam sub-direktori dengan nama direktori yang sama dengan nama parent-modelnya dan lokasi sub-direktori tersebut harus sejajar dengan lokasi dari parent-modelnya

- Namespace Sub-Model

    Sub-model harus berada dalam namespace dengan nama yang sama dengan nama dari parent-modelnya.

- Sub-class dari Parent-Model
    
    Sub-model harus merupakan sub-class dari parent-modelnya.

Berikut adalah contoh dasar dari penulisan source code sebuah Sub-Model:

```php
namespace App\Models\ModelClassName;

/**
 * Class SubModelClassName
 *
 * @package App\Models\ModelClassName
 */
class SubModelClassName extends ModelClassName
{
    /**
     * SubModelClassName::__construct
     */
    public function __construct()
    {
        parent::__construct();
    }
}
```

> Pada contoh diatas SubModelClassName merupakan sub-class atau sub-model dari ModelClassName.

## Anatomy of a Model

Model dasar di O2System Framework terbagi menjadi dua (2) kategori utama yang dipisahkan berdasarkan jenis database yang didukung.


- SQL Base Model
  
    Digunakan untuk bekerja dengan RDBMS database seperti MySql, Microsoft SQL, Postgre SQL dan SQLite.

- NoSQL Base Model
  
    Digunakan untuk bekerja dengan Non-RDBMS database seperti MongoDb atau Cassandra.

Model yang ada di O2System Framework pada dasarnya dapat memiliki kemampuan Object-Relational Mapping (ORM). Namun secara default method-method yang sudah tersedia hanyalah method-method yang berhubungan dengan pencarian atau sering disebut dengan istilah Finder. Sedangkan method-method lainnya tersedia dalam bentuk re-useable code yang di bahasa pemograman PHP dikenal dengan nama [Traits](http://php.net/manual/en/language.oop5.traits.php). Berikut adalah daftar Traits yang sudah tersedia:


|Nama|Deskripsi|
|----|---------|
|AdjacencyTrait|Digunakan untuk membantu bekerja dengan table yang memiliki data struktur adjacency list.
|BeforeAfterTrait|Gunakan trait ini apabila anda memerlukan proses tambahan yang perlu disisipkan sebelum atau sesudah proses dari ModifierTrait (insert, update, delete) dijalankan. Trait ini otomatis digunakan jika anda menggunakan ModifierTrait.
|FinderTrait|Secara default trait ini sudah selalu digunakan pada base model yang berisi method-method yang dipergunakan untuk melakukan proses pengambilan atau pencarian data (read).
|HierarchicalTrait|Digunakan untuk membantu bekerja dengan table yang memiliki data struktur hierarchical list.
|ModifierTrait|Berisi method-method yang dapat dipergunakan untuk melakukan proses perubahan data (insert, update, delete).
|OrderingTrait|Digunakan untuk membantu proses perubahan table yang memiliki data struktur ordering list. Trait ini akan otomatis menjalankan sebuah proses sebelum perubahan data dilakukan. Trait ini baik untuk digunakan bersamaan dengan ModifierTrait.
|RecordTrait|Berisi method-method yang dipergunakan untuk melakukan proses perubahan data-data yang memiliki data struktur record set. Trait ini akan otomatis menjalankan sebuah proses sebelum perubahan data dilakukan. Trait ini baik untuk digunakan bersamaan dengan ModifierTrait.
|RelationTrait|Berisi method-method yang dipergunakan untuk membangun Object-Relational Mapping (ORM).



O2System Framework memilih untuk menyediakannya dalam bentuk re-usable code agar para developer dapat membuat model sesuai dengan kebutuhannya yang disertai penggunaan memory yang optimal dan source code yang dibuat akan menjadi lebih clean.

Secara default ada 4 (empat) jenis hasil yang dihasilkan oleh setiap method-method model, yaitu:

- DataObjects Result

    Setiap pencarian model yang mendapatkan hasil lebih dari satu data, secara default akan mengembalikan hasil berupa DataObjects Result

- DataObjects Result Row

    Setiap pencarian model yang mendapatkan hasil satu data, secara default akan mengembalikan hasil berupa DataObjects Result Row

- Boolean

    Setiap pencarian model (read) yang gagal mendapatkan hasil akan otomatis mengembalikan hasil FALSE dan setiap eksekusi query execute seperti insert, update, delete akan selalu mengembalikan hasil TRUE bila berhasil dan FALSE bila mengalami kegagalan.
    
- Unsigned Numeric
    
    Seluruh eksekusi perhitungan jumlah akan selalu mengembalikan hasil dalam bentuk unsigned numeric.
    
> Jika anda membuat sebuah model custom sendiri sangat direkomendasikan untuk mengembalikan data dengan tipe yang sama seperti yang dijelaskan diatas.

## Load Models

Models tidak dimuat secara default, ada beberapa cara yang dapat dilakukan ketika Models diperlukan, antara lain:

1. Diperlukan di Seluruh Sistem

    Jika anda memerlukan model tertentu di seluruh sistem aplikasi anda, anda dapat mendefinisikannya untuk di-load melalui konfigurasi sistem, dengan cara menambahkannya pada file:
    
    ```
    app/Config/Models.php
    ```

    Secara otomatis model-model yang didefinisikan untuk di-load, akan tersedia dalam models-service dari O2System Framework dan dapat diakses dengan cara:
    
    ```php
    models('modelName')->all();
    ```
2. Diperlukan di salah satu sistem module
    
    Jika anda hanya memerlukan model tertentu hanya pada pada saat module tertentu diakses, anda dapat mendefinisikannya untuk di-load melalui konfigurasi module tersebut, dengan cara membuat file config didalam direktori module tersebut.
    
    ```
    app/Modules/ModuleName/Config/Models.php
    ```
    
    Secara otomatis apabila module tersebut diakses seluruh model-model yang didefinisikan untuk di-load, akan tersedia dalam models-service dari O2System Framework dan dapat diakses dengan cara yang sama sama:
    
    ```php
    models('modelName')->all();
    ```

3. Diperlukan pada saat file tertentu di-load
    Jika anda hanya memerlukan model tertentu hanya pada saat file tertentu diakses, file model tersebut dapat di-load secara manual hanya pada file tersebut cukup dengan cara yang sama jika kita ingin meng-inisiasi sebuah class, berikut contoh dan beberapa alternatif cara pemanggilannya:
    
    Inisiasi Class Model
    
    ```php
    $model = new \App\Models\ModelClassName();
    $result = $model->all();
    ```

4. Inisiasi Static Class Model
    
    ```php
    $result = \App\Models\ModelClassName::all();
    ```

Penting untuk anda perhatikan bahwa melakukan model loading hanya pada saat diperlukan membuat aplikasi anda menjadi lebih ringan karena anda menggunakan memori dengan sangat optimal. Jadi lakukanlah model loading hanya pada saat model tersebut diperlukan saja.

Untuk memuat sebuah sub-model cara yang sama dengan diatas juga bisa dilakukan apabila anda hanya memerlukan sub-model tersebut saja yang akan di-load. Cara termudah untuk mengakses sub-model adalah dengan memanggilnya langsung seperti anda memanggil sebuah object pada model object.

```php
models('modelClassName')->subModelClassName->all();
```

Pemanggilan seperti diatas adalah cara pemanggilan yang paling efektif, karena setiap sub-model yang ada akan otomatis tersedia menjadi property object dari parent-model class sub-model tersebut.