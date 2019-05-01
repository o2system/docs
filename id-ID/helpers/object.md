
# Object

Helper Object berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi Object.

## Loading Helper Object

Helper Object dapat di load dengan perintah berikut ini.

```php
$this->load->helper('object');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Object yang tersedia.

#### get_object_var

Memungkinkan Anda menentukan apakah indeks array diatur dan apakah memiliki nilai. Jika elemen kosong maka akan dikembalikan ke nilai NULL (atau apa pun yang Anda tentukan sebagai nilai default).

```php
get_object_var($property, $object, $default = null)
// 
```
