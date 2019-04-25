# Array

Helper array file berisi beberapa fungsi untuk membantu mengerjakan/manipulasi array dengan mudah.


## Loading Helper Array

Helper Array dapat di load dengan perintah berikut ini.

```php
$this->load->helper('array');
```

## Fungsi yang tersedia

### array_get_value

`array_get_value($key, array $array, $default = null)`

|-----------|--------------------|


```php
$arr = array('biru' => 'Blue', 'kuning' => 'Yellow');
$key = 'biru';
array_get_value($key, $arr);

// Blue
```

### array_get_values

```php
$colors = array('biru' => 'Blue', 'kuning' => 'Yellow', 'hitam' => 'Black');
$key = array('biru', 'kuning' );
array_get_values($key, $colors);

// Array
// (
//     [biru] => Blue
//     [kuning] => Yellow
// )
```

### array_combines


```php
$arr = array('biru' => 'Blue', 'kuning' => 'Yellow', 'hitam' => 'Black');
$key = array('biru' => 'Blue', 'kuning' => 'Sunset' );

array_combines($key, $arr);

// Array
// (
//     [Blue] => Blue
//     [Sunset] => Yellow
// )
```
### array_group

```php

$arr = array('biru' => 'Blue', 'kuning' => 'Yellow', 'hitam' => 'Black');

array_group($arr);

// Array
// (
//     [Blue] => Array
//         (
//             [0] => biru
//         )

//     [Yellow] => Array
//         (
//             [0] => kuning
//         )

//     [Black] => Array
//         (
//             [0] => hitam
//         )

// )
```


### array_filter_recursive
### array_search_recursive
### array_unique_recursive
### array_flatten
### range_price

Fungsi untuk mendapataan jarak kelipatan harga dalam bentuk array.

```php
$min = 200000;
$max = 500000;
$multiplier = 100000;

range_price($min, $max, $multiplier);

// Array
// (
//     [200000] => 300000
//     [100000] => 200000
//     [300000] => 400000
//     [400000] => 500000
// )
```


### range_date
```php

range_date(4)

// Array
// (
//     [0] => 4
// )
```
### range_year

Fungsi untuk mendapatkan jarak kelipatan tahun dalam bentuk array.

```php
$min = 2000;
$max = 2018;
$step = 2;
range_year($min, $max, $step)

// Array
// (
//     [2000] => 2000
//     [2002] => 2002
//     [2004] => 2004
//     [2006] => 2006
//     [2008] => 2008
//     [2010] => 2010
//     [2012] => 2012
//     [2014] => 2014
//     [2016] => 2016
//     [2018] => 2018
// )
```
