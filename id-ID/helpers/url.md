

# Url

Helper Url berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi url.

## Loading Helper Url

Helper Url dapat di load dengan perintah berikut ini.

```php
$this->load->helper('url');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Url yang tersedia.

### base_url

Mengembalikan basis url dasar ke sistem

```php
base_url();

// http://example.com
```

Anda juga bisa menambahkan segment berupa string ataupun array. Serpti contoh berikut ini.

```php
base_url("images/icons/edit.png");

// http://example.com/images/icons/edit.png
```
### domain_url

Fungsi domain_url memiliki kesamaan dengan base url. hanya perbedaanya adalah domain url mampu mengakses url sampai subdomain yang digunakan.

```php
domain_url();

// http://dev.example.com
```

### current_url

Mengembalikan halaman url secara lengkap sesui dengan halaman yang sedang di lihat.


```php
current_url();

// http://example.com/blog/lorem-inpsum
```

### assets_url

Fungsi assets_url menghasilkan alamat url untuk asset yang di tunjuk baik dalam skema HTTP maupun HTTPS.

```php
asset('img/photo.jpg'); 

// http://example.com/assets/img/photo.jpg
```

### storage_url

Fungsi `storage_url` mengembalikan jalur yang sepenuhnya memenuhi syarat ke direktori penyimpanan. Adan dapat menggunakan `storage_url` untuk mengakses data yang ada di dalam media penyimpana aplikasi.

```php
storage_url('app/file.txt');
```

### images_url

Fungsi `images_url` memiliki kesamaan fungsi dengan `storage_url`. hanya fungsi ini langsung mengakses folder images di dalam folder storage.


```php
images_url('app/file.txt');
```

### prepare_url

Fungsi ini akan menambahkan `http: //` jika awalan protokol tidak ada dari URL.

```php
prepare_url('example.com')

// http://exmaple.com
```

### redirect_url

Fungsi redirect_url mengembalikan  redirect HTTP response atau mengembalikan instance redirector jika dipanggil tanpa argumen:

```php
redirect_url('/article/13', 'location', 301);
```