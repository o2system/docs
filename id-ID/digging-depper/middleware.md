# Middleware

Didalam dunia software engineering middleware merupakan sebuah perangkat lunak perantara yang berada diantara kernel dan aplikasi yang salah satu fungsinya adalah sebagai lapisan penyaring permintaan. Pada aplikasi berbasis web middleware middleware merupakan lapisan penyaring permintaan HTTP. 

## Bagaimana Cara Middleware Bekerja?

Framework yang berbeda menerapkan middleware secara berbeda. O2System Framework menerapkan middleware sebagai lapisan konsentris. Lapisan middleware yang pertama diterapkan akan menjadi lapisan middleware terluar dan akan dijalankan dengan metode FIFO (First In First Out) dimulai dari lapisan terluar hingga lapisan terdalam.

![Middleware](http://www.slimframework.com/docs/v3/images/middleware.png)

## Lapisan Built-In Middleware

O2System Framework sudah menyertakan beberapa mekanisme middleware, antara lain:
- Cache Middleware
- Csrf Middleware
- Environment Middleware
- Maintenance Middleware
- Sign On Middleware

## Membuat sebuah middleware