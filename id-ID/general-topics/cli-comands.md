# Cli Command

## Pengantar

O2system Framework memiliki beberapa baris perintah yang di sertakan dalam paket instalasi. cli command ini akan membantu Anda dalam membangun sebuah aplikasi. Untuk melihat semua daftar aplikasi bisa dilakukan perintah berikut ini.

```bash
php o2system -h
```

Setiap perintah disertai dengan "ketetangan" yang menampilkan dan menjelaskan argumen dan opsi yang tersedia. Untuk melihat bantuan setiap perintah awali nama perintah dengan `--help` atau `-h`.

```php
php o2system make -h
```

## perintah baru

Selain perintah yang disediakan dengan O2system, Anda juga dapat membuat perintah kustom sendiri. Perintah biasanya disimpan di direktori `app /Commanders`; namun, Anda bebas memilih lokasi penyimpanan Anda sendiri selama perintah Anda dapat dimuat oleh Komposer.

### Membuat Perintah

Untuk membuat perintah baru, gunakan perintah `php o2system make/commander`. Perintah ini akan membuat kelas perintah baru di direktori `app/ Commanders`. Jangan khawatir jika direktori ini tidak ada di aplikasi Anda, karena itu akan dibuat pertama kali Anda menjalankan perintah `php o2system make/commander`. Perintah yang dihasilkan akan menyertakan set properti dan metode default yang ada pada semua perintah:

```
php artisan make/commander -n SendEmails
```
