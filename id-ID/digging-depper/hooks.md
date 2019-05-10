# Hooks

Didalam dunia software engineering hooks merupakan sebuah perangkat lunak yang merupakan sarana untuk memodifikasi cara kerja sistem inti tanpa meretas sistem inti tersebut. Tidak semua framework menyediakan hooks. O2System Framework menyediakan sarana Hooks agar para developer dapat dengan leluasa memodifikasi cara kerja framework tanpa meretasnya.

## Bagaimana Cara Hooks Bekerja?

Setiap sistem inti dari sebuah framework dibuat dengan megikuti flow tertentu. Untuk dapat melakukan modifikasi sistem inti anda harus terlebih dahulu mengerti flow dari sistem inti tersebut. Pada O2System Framework, hooks dapat ditempatkan pada beberapa point event. Berikut ada adalah daftar dari point-point event:

|Point Event|Deskripsi|
|--|---|
PRE_SYSTEM|Point event ini hanya sistem kernel yang baru dijalankan. Sistem kernel memuat Kernel Services Container yang diikuti dengan dimuatnya Language Service. Sistem framework baru hanya memuat Hooks Service.
POST_SYSTEM|Point event ini dijalankan pada saat sistem framework selesai dimuat. Service-service yang sudah berjalan pada point event ini adalah: 
1. Shutdown Service
2. Logger Service
3. Loader Service
4. Config Container
5. Globals Container
6. Environment Container
7. Models Container
8. Modules Container
9. Cache Service
10. I/O Handler.
11. Parser Service
12. View Service
13. Presenter Service
14. Router Service
15. Session Service
16. Security Protections (CSRF dan XSS)
17. Middleware Service
PRE_CONTROLLER|Point event ini dijalankan pada saat sistem framework telah menemukan controller yang diminta namun controller belum diinisiasi. Point event ini memiliki nama lain yaitu PRE_COMMANDER jika I/O mendeteksi permintaan dilakukan pada command line interface.
POST_CONTROLLER|Point event ini dijalankan pada saat sistem framework telah melakukan inisiasi controller yang diminta. Point event ini memiliki nama lain yaitu POST_COMMANDER jika I/O mendeteksi permintaan dilakukan pada command line interface.

Point-point event diatas dijalankan secara berurutan dengan metode FIFO (First In First Out).

## Mendefinisikan Hook
Pada O2System Framework hook didefinisikan sebagai konfigurasi dari aplikasi yang terdapat pada file `app/Config/Hooks.php`. Hooks didefinisikan sebagai array yang memiliki nilai fungsi lambda / anoymous (atau Closure) .

```php
<?php
$hooks['POST_CONTROLLER'] = function() {
    // do something
};
```

Anda juga dapat mendefinisikan beberapaa panggilan hook sekaligus pada satu point event yang sama, yang akan dieksekusi sesuai dengan urutan yang didefinisikan.

```php
<?php
$hooks['POST_CONTROLLER']= [
    function() {
        // do something
    },
    function() {
        // do something
    },
];
```