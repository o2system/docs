
### Number


Helper Number berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi Number.

## Loading Helper Number

Helper Number dapat di load dengan perintah berikut ini.

```php
$this->load->helper('number');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Number yang tersedia.

#### is_positive

Mengecek sebuah bilangan bernilai possitif.

```php
$number = 1;
is_positive($number);

// (bool) TRUE
 
```

#### is_negative

Mengecek sebuah bilangan bernila negatif.

```php
$number = -1;
is_negative($number)

// (bool) TRUE
```

#### is_odd

Mengecek sebuah bilangan bernilai ganjil

```php
$number = 2;
is_odd($number)

// (bool) TRUE
```

#### is_even

Mengecek sebuah bilangan bernilai genap.

```php
$number = 1;
is_even($number)

// (bool) TRUE
```

#### currency_format

Memgubah bilangan ke dalam sebuah nilai mata uang.

```php
$number  = 123;
currency_format($number, $locale = 'en_US', $currency = 'USD', $add_space = false)

// $ 123
```

#### unit_format

Memformat angka dengan ribuan yang kemudian dikelompokkan dan menambahkan akhiran unit khusus.

```php
$number = 12345;
unit_format($number, $unit = null, $decimals = 0, $decimal_point = '.', $thousands_separator = ',')


// $12,345.00 
```

#### hertz_format

Memformat bilangan menjadi string dengan unit hertz yang sesuai berdasarkan ukuran.

```php
$number = 1234567890;
hertz_format($number);

// 1.1 GHz 
```

#### roman_format

Memformat bilangan menjadi ke dalam bentuk format string roman.

```php
$number = 123;
roman_format($number);

// CXXIII 
```

#### short_format

Menformat bilangan ke dalam kelipatan ribuan.

```php
$number = 100000;
short_format($number, $decimals = 0);

// 100K 
```

#### byte_format

Memformat angka menjadi string dengan satuan byte yang sesuai berdasarkan ukuran.

```php
$number = 100000;
byte_format($number, $decimals = 1);

//  97.7 KB
```

#### ordinal_format

Memformat angka menjadi string ordinal seperti 1st, 2nd, 3rd, 4th.

```php
$number = 5;
ordinal_format($number)
// 5th
```


#### words_format

Memformat bilangan menjadi kata-kata string yang bisa dieja.

```php
$number = 521;
words_format($number, $locale = 'en_US')

// five hundred twenty-one
```

#### zero_fill

Memformat bilangan menjadi string bilangan dengan tambahan nol di depan.

```php
$number = 5;
zero_fill($number, $digits = 2)

// (int) 05
```

#### calculate

```php
$formula = floor(5.2);
calculate($formula);

// (int) 5 
```
