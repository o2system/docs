
# Cookie

Helper Cookie berisi beberapa fungsi yang membantu untuk memanipulasi cookie.

## Loading Helper Common

Secara default helper common telah di load di dalam system. namun jika helper common tidak bisa di panggil maka bisa dengan menggunakan perintah berikut ini.

```php
$this->load->helper('cookie');
```

## Fungsi yang tersedia

Berikut ini merupakan beberapa helper common yang tersedia.

### set_cookie


Fungsi helper ini digunakan untuk mengatur cookie browser dengan lebih mudah.

```php
set_cookie($name)
```
### get_cookie

Fungsi helper ini digunakan untuk medapatkan cookie pada browser Anda. 

```php
get_cookie('o2session');

// qi6k1jv4u90468siurghlan570uihd40
```

### delete_cookie

Fungsi yang memungkinkan untuk menghapus cookie.

```php
delete_cookie('o2session')
```

Jika Adna ingin menghpus cookie dengan beberapa paramater yang  maka bisa menggunakan berikut ini.

```php
delete_cookie($name, $domain, $path, $prefix);
```

Pada dasarnya fungsi ini sama dengan `set_cookie` , hanya dengan beberapa parameter yang perlu di hapus.