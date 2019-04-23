O2system memiliki beberapa method umum yang sering kali digunakan dan mengumpulkannya ke dalam class tools. Karena setiap method tidak memiliki keterkaitan secara langsung dengan method lain di dalam class yang sama, maka method-method ini dibuat dan digunakan secara statik. Cara statik juga akan mempercepat proses pemanggilan masing-masing method ini karena tidak perlu lagi mendeklarasikan instance calss-nya.



## Kernel

### Common

#### is_php

Menentukan apakah versi php sekarang yang digunakan sama dengan atau lebih besar.

```php
is_php(7.2);

// (bool) TRUE
```

#### is_true

Fungsi helper untuk mengecek boolean TRUE

```php
is_true(true)

// (bool) TRUE
```
#### is_false


Fungsi helper untuk mengecek boolean FALSE

```php
is_true(false)

// (bool) FALSE
```

#### is_really_writable

Fungsi helper untuk mengecek sebuah file tersebut bisa di tulis atau tidak.

```php
is_really_writable('file.txt')

// (bool) TRUE
```

#### is_https

sebuah fungsi helper yang digunakan untuk mengecek apakah aplikasi web di akses melalui enkripsi(HTTPS)

```php
is_https()

// (bool) TRUE
```

#### is_cli

Sebuah fungsi untuk mengecek apakah request di panggil datri comand line

```php
is_cli()

// (bool) TRUE
```

#### is_ajax

Sebuah fungsi untuk mengecek apakah request berupa ajax

```php
is_cli()

// (bool) TRUE
```

#### remove_invisible_characters

Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Java\0script.

```php
$str = "Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Java\0script.";

remove_invisible_characters($str);

// Fungsi ini digunakan untuk mencegah karakter null di antara karakter accii seperti Javascript.
```

#### function_usable

Menjalankan pemeriksaan `function_exists()` dan jika esktensi php suhosin telah di muat.

```php
function_usable('is_php');

(bool) TRUE
```

#### apache_request_headers

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

#### path_to_url

mendapatkan  url dari sebuah class controller yang telah di buat.

```php
path_to_url(Hello::class)

// http://localhost:8000/App/Controllers/Hello
```

#### get_namespace

Mendapatkan nama [namespace](https://en.wikipedia.org/wiki/Namespace) dari sebuah class yang di minta.

```php

// App\Controllers\
```
#### get_class_name

Fungsi mendapatkan nama class yang di definisikan.


```php
get_class_name(Hello::class)

// Hello
```

#### prepare_class_name



```php
prepare_class_name(Hello::class)

// App\Controllers\Hello
```

#### prepare_filename

```php
prepare_filename(Hello::class)

// App/Controllers/Hello
```

#### prepare_namespace

```php
prepare_namespace(Hello::class)

// App\Controllers\
```

#### http_parse_headers
#### is_html

```php
$str = "ini html";

is_html($str)

// (bool) TRUE
```

#### is_serialized

```php
$arr = array('O2system', 'Framework');
is_serialized($arr)

// (bool) FALSE

$data = serialize($arr);
is_serialized($data)

// (bool) TRUE
```


#### is_json

Fungsi `is_json` untuk mengecek sebuah ojeck dalam bentuk json.

```php
$myObj->name = "O2System";
$myObj->type = "Framework";
$myJSON = json_encode($myObj);

is_json($myJSON);

// (bool) TRUE
```

#### is_parse_string



#### is_multidimensional_array

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

#### is_associative_array

Fungsi `is_associative_array` adalah fungsi untuk mengecek apakah sebuah arrat merupakan array yang telah mempunyai 

```php
$array = array("Maths"=>95, "Physics"=>90,   
"Chemistry"=>96, "English"=>93,   
"Computer"=>98); 

is_associative_array($array);

// (bool) TRUE
```
#### is_indexed_array

```php
$arr = array('red',  'green',  'white','blue','yellow');
is_indexed_array($arr);

// (bool) TRUE
```
#### error_code_string

Show code message code error.

```php
error_code_string('403');

// FORBIDDEN
```
### Cookie

#### set_cookie

```php
set_cookie($name)

```
#### get_cookie


```php
get_cookie('o2session');

// qi6k1jv4u90468siurghlan570uihd40
```

#### delete_cookie


```php
delete_cookie('o2session')
```

### Inflector

#### readable


```php

```

#### singular

Method `singular()` mengkoversi string ke dalam bentuk tunggal. Fungsi ini hanya mendukung bahasa inggris.

```php
singular('books');

// book

singular('children');

// child
```

#### plural

method `plural()` mengkonversi string ke dalam bentuk jamak. Fungsi ini hanya mendukung dalam bahasa inggris.

```php
plural('book');

// books

```

#### studlycase

Method studlycase mengubah string menjadi huruf besar/kecil

```php
studlycase('books');

// Books

studlycase('Books');

// books
```

#### camelcase

Fungsi untukm mengubah string dalam bentuk camel

```php
camelcase('books_store');

// booksStore
```

#### snakecase

Fungsi untuk mengkonversi string camelCase ke dalam snake_case.

```php
snakecase('books Store');

// books_store
```

#### underscore

Fungsi untuk menggabungkan beberapa kata dengan garis bawah.

```php
underscore('hello world');

// hello_world
```

#### dash

Fungsi untuk menhasilkan url friendly dengan menambahkan `-` pada sebuah string.

```php
dash('hello world');

// hello-world
```

#### is_countable

Fungsi untuk mengecek apakah string bisa di hitung.

```php
is_countable('hello world');

// (bool) TRUE
```

## Framework
### Array
#### array_get_value

```php
$arr = array('biru' => 'Blue', 'kuning' => 'Yellow');
$key = 'biru';
array_get_value($key, $arr);

// Blue
```

#### array_get_values

```php
$arr = array('biru' => 'Blue', 'kuning' => 'Yellow', 'hitam' => 'Black');
$key = array('biru', 'kuning' );
array_get_values($key, $arr);

// Array
// (
//     [biru] => Blue
//     [kuning] => Yellow
// )
```

#### array_combines


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
#### array_group

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


#### array_filter_recursive
#### array_search_recursive
#### array_unique_recursive
#### array_flatten
#### range_price

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


#### range_date
```php

range_date(4)

// Array
// (
//     [0] => 4
// )
```
#### range_year

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

### Datetime


#### timestamp

Fungsi untuk mencetak  waktu sekarang.

```php
timestamp()

// 2019-04-22 17:46:24
```

#### unix_timestamp

Fungsi untuk mencetak waktu sekarang dalam bentuk kode point.

```php
unix_timestamp()

// (int) 1555930056
```
#### format_date

Fungsi untuk mengformat tanggal dalam bentuk hari, tanggal dan waktu.


```php
format_date()

// Monday, 22-April-2019 05:48:55 pm
```

#### parse_date

Fungsi untuk mnegurai tanggal dalam beberapa kelompok seperti hari, tanggal, bulan tahun dll.


```php
parse_date()

// O2System\Spl\DataStructures\SplArrayObject Object
// (
//     [storage:ArrayObject:private] => Array
//         (
//             [t] => 1555930183
//             [d] => 22
//             [D] => Mon
//             [Y] => 2019
//             [y] => 19
//             [am] => Daytime
//             [a] => pm
//             [h] => 05
//             [H] => 17
//             [i] => 49
//             [s] => 43
//             [w] => 1
//             [l] => Monday
//             [m] => 04
//             [n] => 4
//             [F] => April
//             [M] => Apr
//             [e] => Just now
//         )

// )
```

#### day_name

Fungsi untuk mendaptkan nama hari suatu tanggal.

```php
day_name()

// Mon
```

#### month_name

Fungsi untuk mendapatkan nama bulan dari waktu yang di inputkan.

```php
month_name()

// Apr
```
#### time_meridiem

Fungsi untuk mendapatkan waktu dalam bentuk siang atau malam hari.

```php
time_meridiem()

// Daytime
```

#### string_time_elapsed

Fungsi untuk mendapatkan waktu yang telah di lalui.

```php
string_time_elapsed('2001-12-28')

// 17 Years Ago
```

#### dates_between

Fungsi untuk mednapatkan rentang waktu dari dua tanggal yang di ketahui.

```php
dates_between('2001-12-28', '2002-01-01');


// Array
// (
//     [0] => 2001-12-28
//     [1] => 2001-12-29
//     [2] => 2001-12-30
//     [3] => 2001-12-31
//     [4] => 2002-01-01
// ) 
```

#### time_range

Fungsi untuk mengetahui rentan  waktu jam antara dalam batas tertentu

```php
time_range(12, 60)

// Array
// (
//     [12:00 am] => 12:00 am
//     [01:00 am] => 01:00 am
//     [02:00 am] => 02:00 am
//     [03:00 am] => 03:00 am
//     [04:00 am] => 04:00 am
//     [05:00 am] => 05:00 am
//     [06:00 am] => 06:00 am
//     [07:00 am] => 07:00 am
//     [08:00 am] => 08:00 am
//     [09:00 am] => 09:00 am
//     [10:00 am] => 10:00 am
//     [11:00 am] => 11:00 am
//     [12:00 pm] => 12:00 pm
//     [01:00 pm] => 01:00 pm
//     [02:00 pm] => 02:00 pm
//     [03:00 pm] => 03:00 pm
//     [04:00 pm] => 04:00 pm
//     [05:00 pm] => 05:00 pm
//     [06:00 pm] => 06:00 pm
//     [07:00 pm] => 07:00 pm
//     [08:00 pm] => 08:00 pm
//     [09:00 pm] => 09:00 pm
//     [10:00 pm] => 10:00 pm
//     [11:00 pm] => 11:00 pm
// )
```

#### calculate_days

Fungsi untuk menghitung rentang hari.

```php

$start_date = '01-12-2000';
$end_date = '21-12-2000';

calculate_days($start_date, $end_date, $hour = '12:00:00 am');

// (int) 20
```


#### calculate_weeks

Fungsi untuk menghitung rentang minggu.

```php
$start_date = '01-12-2000';
$end_date = '21-12-2001';
```php

calculate_weeks($start_date, $end_date, $hour = '12:00:00 am')

// (int) 55
```


#### is_weekend


Fungsi untuk mengecek tanggal tersebut akhir pekan.

```php
$date = '2019-04-27';
is_weekend($date);


// (bool) TRUE
```


#### is_weekday

Fungsi untuk mengecek tanggal tersebut akhir minggu.

```php
$date = '2019-04-27';
is_weekday($date);


// (bool) FALSE
```


#### get_age

Fungsi untuk mendapatkan umur seseorang.

```php
$date = '2000-04-28';

get_age($date);

// (int) 18 
```

#### get_tenure

Fungsi untuk mendapatkan masa kerja seseorang dari mulai sampai tanggal berakhir.


```php
$date = '2000-04-28';

get_tenure($date);
// 18 years &mdash; 11 months &mdash; 25 days
```


#### time_breakdown

Fungsi untuk mencacah timestamp menjadi sebuah array hari bulan, dari waktu saat ini.

```php
time_breakdown($date)

// Array
// (
//     [years] => 18
//     [months] => 11
//     [weeks] => 3
//     [days] => 2
//     [hours] => 20
//     [minutes] => 3
//     [seconds] => 40
// ) 
```

#### sec2hms

Fungsi untuk mengubah detik ke dalam menit, jam, hari dan seterusnya.

```php
sec2hms(400)

// 0:06:40
```


#### add_time_duration

```php
$date = '2000-04-28 18:19:40';
add_time_duration($date, 12);


// (int) 956963980
```

#### calculate_hours

Fungsi untuk menghitung selisih jam.

```php
$start_time = '12:08:11';
$end_time = '18:01:01';

calculate_hours($start_time, $end_time);

// 05:53
```

#### time_difference

Fungsi untuk perbedaan waktu dan mencacah waktu yang kedalam bentuk array.


```php
$start_time = '2000-04-28 12:08:11';
$end_time = '2001-04-28 18:01:01';
       
// O2System\Spl\DataStructures\SplArrayObject Object
// (
//     [storage:ArrayObject:private] => Array
//         (
//             [days] => 365
//             [years] => 1
//             [months] => 12
//             [hours] => 5
//             [minutes] => 52
//             [seconds] => 50
//         )

// )
```


#### weeks_in_month

Fungsi untuk mengihitung jumalh minggu dalam bulan di tahun tertentu.


```php
weeks_in_month(4, 2000)

// (int) 5
```

#### monday_of_week

Fungsi untuk menhitung jumlah bulan dari awal januari (awal perhitungan) sampai 

```php
monday_of_week(2)

// (int) 21 
```

#### week_number_of_month

```php
week_number_of_month(2, 12, 2019)

// (int) 2
```

#### format_time

```php
format_time(92723762);


// O2System\Spl\DataStructures\SplArrayObject Object
// (
//     [storage:ArrayObject:private] => Array
//         (
//             [days] => 1073
//             [years] => 2
//             [months] => 35
//             [hours] => 4
//             [minutes] => 36
//             [seconds] => 2
//         )

// )
```

#### now

```php
now()

// (int) 1555933030
```

#### mdate

```php
$datestring = 'Year: %Y Month: %m Day: %d - %h:%i %a';
$time = time();

mdate($datestring, $time);

// Year: 2019 Month: 04 Day: 22 - 06:42 pm
```

#### timespan


```php
$post_date = '1079621429';
$now = time();
$units = 2;
timespan($post_date, $now, $units);

// 
```


#### days_in_month

```php
days_in_month(06, 2005);
// 
```


#### local_to_gmt


```php
local_to_gmt(time());

// 
```

#### gmt_to_local


```php
$timestamp = 1140153693;
$timezone  = 'UM8';
$daylight_saving = TRUE;
gmt_to_local($timestamp, $timezone, $daylight_saving);
// 
```

#### mysql_to_unix

```php
mysql_to_unix('20061124092345');
// 
```

#### unix_to_human

```php
$now = time();
echo unix_to_human($now); // U.S. time, no seconds
echo unix_to_human($now, TRUE, 'us'); // U.S. time with seconds
echo unix_to_human($now, TRUE, 'eu'); // Euro time with seconds
// 
```

#### human_to_unix

```php
$now = time();
$human = unix_to_human($now);
$unix = human_to_unix($human);
// 
```

#### nice_date

```php
$bad_date = '199605';
// Should Produce: 1996-05-01
$better_date = nice_date($bad_date, 'Y-m-d');

$bad_date = '9-11-2001';
// Should Produce: 2001-09-11
$better_date = nice_date($bad_date, 'Y-m-d');
// 
```

#### timezones

```php
timezones('UM5');
// 
```

#### date_range_unix

```php

// 
```

### Html

#### tag

```php
$tagName = 'label';
$content = 'title';
$attributes = array('for' => 'title', 'class' => 'control-label');

tag($tagName, $contents, $attributes)

// <label for="title" class="control-label">Title </label> 
```

#### video

```php
$src = 'video.mp4';
video($src)

// <video width="320" height="240" controls> VIDEO_NOT_SUPPORTED </video>
```

#### audio

```php
$src = 'audio.mp3';
audio($src, array $attributes = [])

// <audio controls>
// AUDIO_NOT_SUPPORTED
// </audio> 
```

#### canvas

```php

canvas($attributes)

// <canvas>
// CANVAS_NOT_SUPPORTED
// </canvas> 
```

#### heading

```php
$textContent = 'title';
$level = 2;
$attributes = array('class' => 'heading');
heading($textContent, $level, $attributes)

// <h2 class="heading">
// title
// </h2>
```

#### ul

```php
$list = array('Merah', 'kuning', 'Biru', 'Hitam', 'Putih' );
$attributes = array('class' => 'list-style');
ul($list, $attributes)

// 
```

#### ol

```php
$list = array('Merah', 'kuning', 'Biru', 'Hitam', 'Putih' );
$attributes = array('class' => 'list-style');
ol($list, $attributes)

// <ol class="list-style">
// <li>Merah</li>
// <li>kuning</li>
// <li>Biru</li>
// <li>Hitam</li>
// <li>Putih</li>
// </ol>
```

#### img

```php
$src = 'image.jpg';
$alt = 'title';
$attributes = array('class' => 'list-style');
img($src, $alt, $attributes)

// <ul class="list-style">
// <li>Merah</li>
// <li>kuning</li>
// <li>Biru</li>
// <li>Hitam</li>
// <li>Putih</li>
// </ul>
```

#### meta

```php
$meta = 'generator';
$content = 'O2CMS - Liquid Content Management System';
$type = 'name';

meta($meta, $content, $type)
// <meta name="generator" content="O2CMS - Liquid Content Management System">
```

#### parse_attributes

```php
parse_attributes($string)
// 
```

#### remove_tags

```php
$html = = "<div> Anim pariatur cliche reprehenderit.</div>";
$tags = 'div';
remove_tags($html, $tags)

// Anim pariatur cliche reprehenderit.
```

#### extract_tag

```php
extract_tag($html, $tag = 'div')
// Anim pariatur cliche reprehenderit.
```

### Number

#### is_positive

```php
is_positive($number)
// 
```

#### is_negative

```php
is_negative($number)
// 
```

#### is_odd

```php
is_odd($number)
// 
```

#### is_even

```php
is_even($number)
// 
```

#### currency_format

```php

currency_format($number, $locale, $currency = 'USD', $add_space)
// 
```

#### unit_format


```php
unit_format($number, $unit, $decimals, $decimal_point, $thousands_separator)
// 
```

#### hertz_format

```php
hertz_format($number)
// 
```

#### roman_format


```php
roman_format($number)
// 
```

#### short_format

```php
short_format($number, $decimals = 0)
// 
```

#### byte_format

```php
byte_format($number, $decimals = 1)
// 
```

#### ordinal_format

```php
ordinal_format($number)
// 
```


#### words_format

```php
words_format($number, $locale = 'en_US')
// 
```

#### zero_fill

```php
zero_fill($number, $digits = 2)
// 
```

#### calculate

```php
calculate($formula)
// 
```

### Object

#### get_object_var

```php
get_object_var($property, $object, $default = null)
// 
```
### Security

#### strip_image_tags

```php
strip_image_tags($source_code)
// 
```

#### strip_cdata

```php
strip_cdata($source_code)
// 
```


#### strips_all_tags

```php
strips_all_tags($source_code)
// 
```

#### strips_tags

```php
strips_tags($source_code, $disallowed_tags = 'script|style|noframes|select|option', $allowed_tags = '')
// 
```

#### strip_word_doc

```php
strip_word_doc($source_code, $allowed_tags = '')
// 
```

#### strip_slashes_recursive

```php
strip_slashes_recursive($string)
// 
```


#### strip_comments

```php
strip_comments($source_code)
// 
```

#### clean_white_space
```php
clean_white_space($source_code)
// 
```

#### encode_php_tags
```php
encode_php_tags($string)
// 
```

#### escape_html
```php
escape_html($source_code, $encoding = 'UTF-8', $double_encode = true)
// 
```
### String

#### str_echo

```php
str_echo($string, $prefix = null, $suffix = null, $glue = '')
// 
```

#### str_email

```php
str_email($string)
// 
```

#### str_alphanumeric

```php
str_alphanumeric($string)
// 
```

#### str_numeric

```php
str_numeric($string)
// 
```

#### str_truncate

```php
str_truncate($string, $limit = 25, $ending = '')
// 
```

#### str_shorten

```php
str_shorten($string, $limit = 25)
// 
```

#### str_obfuscate

```php
str_obfuscate($string)
// 
```

#### str_symbol_to_entities

```php
str_symbol_to_entities($string)
// 
```

#### str_strip_slashes

```php
str_strip_slashes($string)
// 
```

#### str_quote_strip

```php
str_quote_strip($str)
// 
```

#### str_filter_char


```php
str_quote_to_entities($string)
// 
```

#### str_rand

```php
str_rand($type = 'alnum', $length = 8)
// 
```


#### str_inc

```php

// 
```

#### str_alt

```php

// 
```

#### str_char_to_ascii


```php

// 
```

#### str_entities_to_ascii

```php

// 
```

#### str_ascii_to_entities

```php

// 
```

### Text

#### text_split
#### text_columns
#### text_wrap
#### text_trim
#### text_word_limiter
#### text_character_limiter
#### text_censored
#### text_highlight_phrase
#### text_word_wrap
#### text_ellipsis
#### text_excerpt


### Url

#### base_url
#### domain_url
#### current_url
#### assets_url
#### storage_url
#### images_url
#### prepare_url
#### redirect_url