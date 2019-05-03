# Konfigurasi


## Pengantar

Semua file konfigurasi untuk framework O2System disimpan di direktori `app/Config`. Setiap opsi didokumentasikan, jadi silakan melihat-lihat file dan membiasakan diri dengan opsi yang tersedia untuk Anda.

## Konfigurasi Lingkungan

Developer biasanya memiliki konfigurasi yang berbeda untuk setiap Lingkungan aplikasi yang di buat, untuk lingkungan *development*, *testing*, atau untuk *production*. Misalnya Anda mungkin ingin menggunkana driver cache yang berbeda pada saat di lingkungan development di server lokal dari server production.

Di O2System hal ini sangatlah mudah di lakukan, O2System akan memanfaatkan file konfigurasi di yang ada di direktori `app/Config/Development` jika Anda sedang melakukan pengerjaan di local. direktori ini tidak boleh di commit karena setiap developer mungkin memiliki konfigurasi lingkungan yang berbeda.

Seringkali bermanfaat untuk memiliki nilai konfigurasi yang berbeda berdasarkan pada lingkungan di mana aplikasi berjalan. Misalnya, Anda mungkin ingin menggunakan driver cache yang berbeda secara lokal dari pada server produksi Anda.

Anda dapat membuat konfigurasi yang berbeda tergantung konfigurasi linkunganya di file `public/index.php` 

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

Pengaturan lingkungan akan berpengaruh terhadap beberapa hal seperti logging dan laporan kesalahan. Pengaturan lingkungan bisa di atur dengan beberapa nilai 

* development
* testing
* production
