## Pengantar

Session adalah sebuah varibel sementara yang diletakkan di server. Di mana PHP bisa mengambil nilai yang tersimpan di server walaupun kita membuka halaman baru. Biasanya session akan hilang jika anda menutup browser.

Fungsi session adalah untuk melakukan aktivitas yang berhubungan dengan interaksi user pada sebuah web server php. O2System menyediakan beberapa session backend yang dapat di akses dengan mudah. O2System mendukung beberapa backend yang popular seperti Redis, Mecmcache, Apc, Apcu


Dukungan untuk backend populer seperti [Memcached](https://memcached.org), [Redis](https://redis.io), dan basis data dimasukkan di luar kotak.

### Konfigurasi

File konfigurasi sesi disimpan di `app/Config/ session.php`. Pastikan untuk meninjau opsi yang tersedia untuk Anda dalam file ini. Secara default, O2System dikonfigurasi untuk menggunakan driver sesi `file`, yang akan bekerja dengan baik untuk banyak aplikasi. Dalam aplikasi produksi, Anda dapat mempertimbangkan untuk menggunakan driver `memcached` atau` redis` untuk kinerja sesi yang lebih cepat.

Opsi konfigurasi `driver` sesi menentukan di mana data sesi akan disimpan untuk setiap permintaan. O2System mengirim dengan beberapa pembalap hebat di luar kotak:

<div class = "content-list" markdown = "1">
- `file` - sesi disimpan di` storage / framework / sesi`.
- `cookie` - sesi disimpan dalam cookie yang aman dan terenkripsi.
- `database` - sesi disimpan dalam database relasional.
- `memcached` /` redis` - sesi disimpan di salah satu toko berbasis cache yang cepat ini.
- `array` - sesi disimpan dalam array PHP dan tidak akan bertahan.
</div>