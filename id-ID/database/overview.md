# Overview

O2system mampu berinteraksi dengan beberapa RDBMS dengan raw SQL, quiry builder dan ORM. Saat ini O2system mendukung beberapa.

 - MySQL
 - SQLite
 - MongoDB (no SQL)


## Konfigurasi

Konfigurasi database untuk aplikasi terleteak di `app/Config/Database.php`. Dalam file ini terdapat beberapa paramater untuk menentukan koneksi dengan database Anda, serta untuk menentukan koneksi yang harus di gunakan secara default.

Secara default, 

```php
$database[ 'default' ] = [
    'driver'       => 'mysql',
    'dsn'          => '',
    'hostname'     => 'localhost',
    'port'         => 3306,
    'username'     => 'root',
    'password'     => 'mysql',
    'database'     => 'o2system_cms',
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
    'debugEnable' => false,
];
```

Keterangan

|Variable	|Tipe Data	|Keterangan|
|-----------|-----------|----------
|driver	|string	|Pilihan driver database yang akan digunakan. Pilihannya adalah: mysql, pgsql, sqlite, cubrid atau mongodb
|host|	string	|Host database server.
|user|	string	|Username yang digunakan untuk koneksi ke database server.
|password|	string|	Password yang digunakan untuk konesi ke database server.
|database|	string|	Nama database yang akan digunakan.
