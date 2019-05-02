# Helpers

## Pengenalan

Helpers merupakan sekumpulan fungsi yang dibuat untuk membantu memberikan kemudahan dalam pengembangan aplikasi yang dikelompokkan dalam satu file sesuai dengan kategori dan peruntukkannya.

Helpers tidak ditulis dalam format Object Oriented atau berupa Class melainkan dalam bentuk yang sederhana yaitu sebagai function yang sifatnya prosedural. Setiap helper function dibuat untuk membantu satu dan dapat tanpa ketergantungan pada fungsi helper lainnya.

## Lokasi Direktori

Seluruh file Helper harus ditempatkan di dalam direktori khusus dengan nama direktor Helpers. Direktori Helpers dapat ditempatkan pada direktori utama aplikasi anda ataupun oleh modul-modul dari aplikasi anda.

## Helper yang tersedia

Secara default O2System Framework sudah menyediakan beberapa Helpers.

Berikut adalah daftar file-file helper yang sudah tersedia:


- Kernel Helpers
  - [Common Helper](/docs/helpers/common)
  - [Cookie Helper](/docs/helpers/cookie)
  - [Inflector Helper](/docs/helpers/inflector)
  - [Kernel Helper]()
  
- Framework Helpers
  - [Array Helper](/docs/helpers/array)
  - [Datetime Helper](/docs/helpers/datetime)
  - [Framework Helper](/docs/helpers/framework)
  - [Html Helper](/docs/helpers/html)
  - [Number Helper](/docs/helpers/number)
  - [Security Helper](/docs/helpers/security)
  - [String Helper](/docs/helpers/string)
  - [Text Helper](/docs/helpers/text)
  - [Url Helper](/docs/helpers/url)
  
## Extending Helpers

Perluasan bertujuan untuk menambahkan function-function baru dari yang sudah tersedia di O2System Framework, untuk melakukan perluasan dari helper-helper yang sudah tersedia di O2System Framework sangatlah mudah.

Anda cukup memberi nama file helper extension anda dengan nama yang sama dengan nama helper O2System Framework yang ingin anda perluas dan
menyimpannya dalam direktori aplikasi / module anda:

```
app/Helpers/HelperName.php
```

## Adding Helpers

Selain memperluas helper yang sudah ada, anda juga dapat menambahkan helper-helper baru dengan cara membuat sendiri helper yang dibutuhkan oleh aplikasi anda. Nama helper tersebut dapat anda tentukan sendiri, yang perlu anda perhatikan adalah cara penulisan nama file helper tersebut harus sesuai dengan standar PSR-0 dan penulisan code helper tersebut harus sesuai dengan standar PSR-1 dan PSR-2. Hal terakhir yang perlu anda perhatikan adalah anda harus menyimpan file helper baru anda kedalam folder Helpers dari aplikasi / module anda.


Cara termudah membuat helper pertama kali adalah melalui O2System Console, dengan perintah:

```bash
php o2system make:helper --name=HelperName
```

Option-option yang tersedia lainnya adalah:



|Opsi   |pintasan   |Term   |Deskripsi
|-------|-----------|-------|-------|
|--name   |-n   |required   |Menentukan nama dari Helper   |
|--path|-p|optional|Menentukan penempatan di direktori lain, selain direktori default, yaitu `app/Helpers/`



Berikut ini adalah contoh penulisan source code helper:

```php
if(!function_exists('your_function_name')) {
    /**
     * your_function_name
     * 
     * Function description
     * 
     * @param mixed $param
     */
    function your_function_name( $param ) {
        // your function process here
    }
}
```

## Load Helpers

Helpers tidak dimuat secara default, ada beberapa cara yang dapat dilakukan ketika memerlukan kehadiran Helpers untuk membantu yang dapat dikategorikan pada saat memerlukannya, antara lain:

1. Diperlukan di Seluruh Sistem

    Jika anda memerlukan kehadiran helper tertentu di seluruh sistem aplikasi anda, anda dapat mendefinisikannya untuk di-load melalui konfigurasi sistem, dengan cara menambahkannya pada file:
    
    `app/Config/Helpers.php`

2. Diperlukan di salah satu sistem module

    Jika anda hanya memerlukan kehadiran helper tertentu hanya pada pada saat module tertentu diakses, anda dapat mendefinisikannya untuk di-load melalui konfigurasi module tersebut, dengan cara membuat file config didalam direktori module tersebut.

    `app/Modules/ModuleName/Config/Helpers.php`
    
3. Diperlukan pada saat file tertentu di-load

    Jika anda hanya memerlukan kehadiran helper tertentu hanya pada saat file tertentu diakses, file helper tersebut dapat di-load secara manual hanya pada file tersebut dengan perintah:

4. Single Helper
    
    `loader()->helper('HelperName');`

5. Multiple Helpers

    `loader()->helpers(['HelperName','OtherHelperName']);`
    
Penting untuk anda perhatikan bahwa melakukan helper loading hanya pada saat diperlukan membuat aplikasi anda menjadi lebih ringan karena anda menggunakan memori dengan sangat optimal. Jadi lakukanlah helper loading hanya pada saat helper tersebut diperlukan saja.


