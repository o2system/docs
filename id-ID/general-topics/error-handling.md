# Penanganan Eror

O2System memungkinkan Anda membuat pelaporan kesalahan ke dalam aplikasi Anda menggunakan fungsi yang dijelaskan di bawah ini. Selain itu, ia memiliki kelas logging kesalahan yang memungkinkan pesan kesalahan dan debugging disimpan sebagai file teks.

> Secara default, O2System menampilkan semua kesalahan PHP. Anda mungkin ingin mengubah perilaku ini setelah pengembangan Anda selesai.


Tidak seperti kebanyakan sistem di O2System, fungsi kesalahan adalah antarmuka prosedural sederhana yang tersedia secara global di seluruh aplikasi. Pendekatan ini memungkinkan pesan kesalahan dipicu tanpa harus khawatir tentang pelingkupan kelas / fungsi.
