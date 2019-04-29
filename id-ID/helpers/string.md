# String

Helper String berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi String.

## Loading Helper String

Helper String dapat di load dengan perintah berikut ini.

```php
$this->load->helper('string');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper String yang tersedia.

### str_echo


```php
str_echo($string, $prefix = null, $suffix = null, $glue = '');
```

### str_email

Fungsi sederhanan untuk menyimpan tampilan alamat email.

```php
$string = "email@o2system.id";
str_email($string);

// email [at] o2system [dot] id
```

### str_alphanumeric

Menghapus kareakter yang bukan alphanumerik.

```php
$string = "halo 1321312542342 !@#$%^&*()_+";
str_alphanumeric($string)

// halo 1321312542342
```

### str_numeric

Menghapus karakter non numeric.

```php
$string = "halo 1321312542342 !@#$%^&*()_+";
str_alphanumeric($string)

// (int) 1321312542342
```

###  str_truncate

Memotong string hingga panjang tertentu.

```php
$string = "Occaecat nulla dolore adipisicing fugiat.";
str_truncate($string, $limit = 25, $ending = '')
// Occaecat nulla dolore
```

### str_shorten

Persingkat string dengan batas, jika string terlalu panjang akan dipersingkat di tengah.

```php
$string = "Occaecat nulla dolore adipisicing fugiat.";
str_shorten($string, $limit = 25);

// Occaecat nul ... cing fugiat.
```

### str_obfuscate


```php
$string = "O2";
str_obfuscate($string);

// &#79;&#50;
```

### str_symbol_to_entities

Mengubah simbol karakter tinggi ke entitas html masing-masing.

```php
$string = "®";
str_symbol_to_entities($string);

// &reg;
```

### str_strip_slashes

Menghapus garis miring terbalik yang terkandung dalam string atau dalam array.

```php
$string = "Hallo, \ World";
str_strip_slashes($string);

// Hallo, World
```

### str_quote_strip

Menghpus tanda petik satu atau dobel di dalam string.

```php
$string = "'How Are You', 'Daddy' ";

str_quote_strip($string)

// How Are You, Daddy 
```

### str_quote_to_entities

Mengubah tanda petik satu atau double ke dalam bentuk simnbol entity.

```php
$string = "'How Are You', 'Daddy' ";

str_quote_to_entities($string)

// &#39;How Are You&#39;, &#39;Daddy&#39; 
```


### str_filter_char


```php
$str = "Occaecat nulla dolore,,,, adipisicing fugiat.";
str_filter_char($str, $character = ',', $trim = false)

// Occaecat nulla dolore, adipisicing fugiat.
```

### str_rand

MemBuat string secara acak, sangat berguna untuk menghasilkan kata sandi atau hash.


```php
str_rand($type = 'alnum', $length = 8)

// hPlr8SyR
```

### str_inc

Tambahkan _1 ke string atau tambahkan angka akhir untuk memungkinkan _2, _3, dll.

```php
$string = "Occaecat nulla dolore adipisicing fugiat.";
str_inc($string, $separator = '_', $first = 1);

// Occaecat nulla dolore adipisicing fugiat._1
```

### str_alt

### str_chars_to_ascii

Mengubah karakter asing beraksen ke ASCII.

```php
$string = "ÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏ";
str_chars_to_ascii($string)

// AAAAAeAAECEEEEIIII
```
### str_entities_to_ascii

Mengembalikan karakter entity ke dalam kode ASCII.

```php
$string = "‰€™";
str_chars_to_ascii($string)

// &#8240;&#8364;&#8482;
```