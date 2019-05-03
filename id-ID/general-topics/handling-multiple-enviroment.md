# Penanganan beberapa Enviroment

Developer sering memisahakan sistem yang berbeda tergantung pada aplikasi berjalan baik dilingkungan pada saat *development* atau *production*. Misalnya, output kesalahan verbose adalah sesuatu yang akan berguna saat mengembangkan aplikasi, tetapi juga dapat menimbulkan masalah keamanan ketika "live".


Secara default, O2System hadir dengan konstanta lingkungan yang diatur untuk menggunakan nilai yang diberikan dalam Front End Controller, jika tidak, defaultnya adalah ‘development’. Di bagian atas index.php, Anda akan melihat:

```php
if ( ! defined( 'ENVIRONMENT' ) ) {
    /**
     * Environment Stage
     *
     * @value DEVELOPMENT|TESTING|PRODUCTION
     */
    define( 'ENVIRONMENT', 'DEVELOPMENT' );

    /**
     * Environment Debug Stage
     *
     * @value DEVELOPER|TESTER|PUBLIC
     */
    $_ENV[ 'DEBUG_STAGE' ] = 'DEVELOPER';
}
```
## Laporan Eror

Mengatur konstanta `DEVELOPMENT` ke nilai 'DEVELOPER' akan menghasilkan semua eror pada kode PHP dirender ke browser saat itu terjadi. Sebaliknya, menyetel konstanta ke 'PRODUCTION' akan menonaktifkan semua output eror.