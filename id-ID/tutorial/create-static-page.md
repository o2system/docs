# Membuat Halaman Static

Dalam membangun sebuah website salah satu isi yang selalu ada adalah halaman web dengan konten tetap atau biasa lebih akrab disebut static page. 
Static page merupakan sebuah halaman web berisi source code HTML dan cenderung bersifat tetap atau jarang berubah-ubah. 
Berikut langkah-langkah membuat halaman statis pada O2System Framework, sebagai contoh kasus kita akan membuat sebuah halaman statis yang berisikan informasi profil perusahaan. 

## Membuat Halaman

Buatlah sebuah file page dengan ekstensi phtml, simpanlah pada direktori `resources/pages`.

<h1 class="page-header">About Us</h1>
<p class="page-content">
    This is about us page.
</p>


Beberapa hal yang harus diperhatikan:
1. Nama file harus berekstensi phtml
2. File harus disimpan pada directory `resources/pages`.
3. Filename harus ditulis dengan format StudlyCaps.

## Mengakses Halaman

Anda dapat langsung mengakses halaman ini melalui browser anda dengan mengetikkan alamat URL seperti dibawah ini:

```
http://localhost:8000/about-us
```

Perhatikan format penulisan segmentasi url about-us diatas yang berformat dash. Format ini merupakan cara penulisan alamat segmentasi url yang paling dianjurkan karena bersifat Search Engine Friendly (SEF) URL.

Untuk penggunaan lebih lanjut anda dapat membacanya pada bagian pendalaman [Page]().
