
# Common

Helper Common merupakan beberapa fungsi helper yang digunakan untuk mengecek system, boolean, permission dll.

## Loading Helper Common

Secara default helper common telah di load di dalam system. namun jika helper common tidak bisa di panggil maka bisa dengan menggunakan perintah berikut ini.

```php
$this->load->helper('common');
```
## Fungsi yang tersedia

Berikut ini merupakan beberapa helper common yang tersedia.

### is_php

Menentukan apakah versi php sekarang yang digunakan sama dengan atau lebih besar.

```php
is_php(7.2);

// (bool) TRUE
```

### is_true

Fungsi helper untuk mengecek boolean TRUE

```php
is_true(true)

// (bool) TRUE
```
### is_false


Fungsi helper untuk mengecek boolean FALSE

```php
is_true(false)

// (bool) FALSE
```

### is_really_writable

Fungsi helper untuk mengecek sebuah file tersebut bisa di tulis atau tidak.

```php
is_really_writable('file.txt')

// (bool) TRUE
```

### is_https

sebuah fungsi helper yang digunakan untuk mengecek apakah aplikasi web di akses melalui enkripsi(HTTPS)

```php
is_https()

// (bool) TRUE
```

### is_cli

Sebuah fungsi untuk mengecek apakah request di panggil datri comand line

```php
is_cli()

// (bool) TRUE
```

### is_ajax

Sebuah fungsi untuk mengecek apakah request berupa ajax

```php
is_cli()

// (bool) TRUE
```

### remove_invisible_characters

Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Java\0script.

```php
$str = "Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Java\0script.";

remove_invisible_characters($str);

// Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Javascript.
```

### function_usable

Menjalankan pemeriksaan `function_exists()` dan jika esktensi php suhosin telah di muat.

```php
function_usable('is_php');

(bool) TRUE
```

### apache_request_headers

Mendapatkan nilai [apache header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) dari sebuah request client.

```php

apache_request_headers()

Array
(
[COOKIE] => o2session=q21chpineedpsl4qta72l35ehctf9ipv
[ACCEPT-LANGUAGE] => en-US,en;q=0.9
[ACCEPT-ENCODING] => gzip, deflate
[ACCEPT] => text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3
[USER-AGENT] => Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.103 Safari/537.36
[UPGRADE-INSECURE-REQUESTS] => 1
[CACHE-CONTROL] => max-age=0
[CONNECTION] => keep-alive
[HOST] => localhost:8000
)
```

### path_to_url

mendapatkan  url dari sebuah class controller yang telah di buat.

```php
path_to_url(Hello::class)

// http://localhost:8000/App/Controllers/Hello
```

### get_namespace

Mendapatkan nama [namespace](https://en.wikipedia.org/wiki/Namespace) dari sebuah class yang di minta.

```php

// App\Controllers\
```
### get_class_name

Fungsi mendapatkan nama class yang di definisikan.


```php
get_class_name(Hello::class)

// Hello
```

### prepare_class_name



```php
prepare_class_name(Hello::class)

// App\Controllers\Hello
```

### prepare_filename

```php
prepare_filename(Hello::class)

// App/Controllers/Hello
```

### prepare_namespace

```php
prepare_namespace(Hello::class)

// App\Controllers\
```

### http_parse_headers
### is_html

```php
$str = "ini html";

is_html($str)

// (bool) TRUE
```

### is_serialized

```php
$arr = array('O2system', 'Framework');
is_serialized($arr)

// (bool) FALSE

$data = serialize($arr);
is_serialized($data)

// (bool) TRUE
```


### is_json

Fungsi `is_json` untuk mengecek sebuah ojeck dalam bentuk json.

```php
$myObj->name = "O2System";
$myObj->type = "Framework";
$myJSON = json_encode($myObj);

is_json($myJSON);

// (bool) TRUE
```

### is_parse_string



### is_multidimensional_array

Fungsi `is_multidimensional_array` digunakan untuk mengecek apakah sebuah array dalam bentuk array multidimensi.

```php
$cars = array
(
array("Volvo",22,18),
array("BMW",15,13),
array("Saab",5,2),
array("Land Rover",17,15)
);

is_multidimensional_array($cars);

// (bool) TRUE
```

### is_associative_array

Fungsi `is_associative_array` adalah fungsi untuk mengecek apakah sebuah arrat merupakan array yang telah mempunyai 

```php
$array = array("Maths"=>95, "Physics"=>90,   
"Chemistry"=>96, "English"=>93,   
"Computer"=>98); 

is_associative_array($array);

// (bool) TRUE
```
### is_indexed_array


```php
$arr = array('red',  'green',  'white','blue','yellow');
is_indexed_array($arr);

// (bool) TRUE
```
### error_code_string

Menampilkan pesan kode error.

```php
error_code_string('403');

// FORBIDDEN
```
