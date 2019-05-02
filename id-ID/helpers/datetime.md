
# Datetime

Helper Datetime berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi waktu.

## Loading Helper Array

Helper Datetime dapat di load dengan perintah berikut ini.

```php
$this->load->helper('datetime');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Datetime yang tersedia.

### timestamp

Fungsi untuk mencetak  waktu sql.

```php
timestamp()

// 2019-04-22 17:46:24
```

### unix_timestamp

Fungsi untuk mencetak waktu sekarang dalam bentuk kode point(unix).

```php
unix_timestamp()

// (int) 1555930056
```
### format_date

Fungsi untuk mengformat tanggal dalam bentuk hari, tanggal dan waktu.


```php
format_date()

// Monday, 22-April-2019 05:48:55 pm
```

### parse_date

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

### day_name

Fungsi untuk mendapatkan nama hari suatu tanggal.

```php
day_name()

// Mon
```

### month_name

Fungsi untuk mendapatkan nama bulan dari waktu yang di inputkan.

```php
month_name()

// Apr
```
### time_meridiem

Fungsi untuk mendapatkan waktu dalam bentuk siang atau malam hari.

```php
time_meridiem()

// Daytime
```

### string_time_elapsed

Fungsi untuk mendapatkan waktu yang telah di lalui.

```php
string_time_elapsed('2001-12-28')

// 17 Years Ago
```

### dates_between

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

### time_range

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

### calculate_days

Fungsi untuk menghitung rentang hari.

```php

$start_date = '01-12-2000';
$end_date = '21-12-2000';

calculate_days($start_date, $end_date, $hour = '12:00:00 am');

// (int) 20
```


### calculate_weeks

Fungsi untuk menghitung rentang waktu minggu.

```php
$start_date = '01-12-2000';
$end_date = '21-12-2001';


calculate_weeks($start_date, $end_date, $hour = '12:00:00 am')

// (int) 55
```


### is_weekend


Fungsi untuk mengecek tanggal tersebut akhir pekan.

```php
$date = '2019-04-27';
is_weekend($date);


// (bool) TRUE
```


### is_weekday

Fungsi untuk mengecek tanggal tersebut akhir minggu.

```php
$date = '2019-04-27';
is_weekday($date);


// (bool) FALSE
```


### get_age

Fungsi untuk mendapatkan umur seseorang.

```php
$date = '2000-04-28';

get_age($date);

// (int) 18 
```

### get_tenure

Fungsi untuk mendapatkan masa kerja seseorang dari mulai sampai tanggal berakhir.


```php
$date = '2000-04-28';

get_tenure($date);
// 18 years &mdash; 11 months &mdash; 25 days
```


### time_breakdown

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

### sec2hms

Fungsi untuk mengubah detik ke dalam menit, jam, hari dan seterusnya.

```php
sec2hms(400)

// 0:06:40
```


### add_time_duration

```php
$date = '2000-04-28 18:19:40';
add_time_duration($date, 12);


// (int) 956963980
```

### calculate_hours

Fungsi untuk menghitung selisih jam.

```php
$start_time = '12:08:11';
$end_time = '18:01:01';

calculate_hours($start_time, $end_time);

// 05:53
```

### time_difference

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


### weeks_in_month

Fungsi untuk mengihitung jumalh minggu dalam bulan di tahun tertentu.


```php
weeks_in_month(4, 2000)

// (int) 5
```

### monday_of_week

Fungsi untuk menhitung jumlah bulan dari awal januari (awal perhitungan) sampai 

```php
monday_of_week(2)

// (int) 21 
```

### week_number_of_month

```php
week_number_of_month(2, 12, 2019)

// (int) 2
```

### format_time

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

### now

Mencetak waktu saat ini berdasarkan referensi waktu lokal server atua zona waktu yang di dukung oleh php.

```php
now()

// (int) 1555933030
```

### mdate

Fungsi ini identik dengan fungsi `date()` PHP, kecu
```php
$datestring = 'Year: %Y Month: %m Day: %d - %h:%i %a';
$time = time();

mdate($datestring, $time);

// Year: 2019 Month: 04 Day: 22 - 06:42 pm
```

> jika timestamp tidak menyertakan paramater detik maka akan menggunakan waktu sekarang yang digunakan.

### timespan

Menformat waktu timestamp unix sehingga menjadi tampak seperti berikut ini.

```
1 Year, 10 Months, 2 Weeks, 5 Days, 10 Hours, 16 Minutes
```

Parameter pertama harus berisi waktu UNIX , paramater kedua berisi berisi waktu yang lebih besar dari pada paramter pertama. sedangakan untuk paramater ketiga bersifat oppsional untuk membatasi jumlah unit waktu yang di tampilkan.

Keuntungan mendugnakn fungsi ini adalah Anda tidak perlu khawatir akan keluar karakter apapun yang bukan kode tanggal, sperti yang biasanya harus Anda lakukan pada fungsi `date()`.

```php
$post_date = '1079621429';
$now = time();
$units = 2;
timespan($post_date, $now, $units);

// 15 Years, 1 Month
```


### days_in_month

Mengembalikan jumlah hari dalam bulan/tahun tertentu. Menggunakan tahun kabisat.

```php
days_in_month(06, 2005);

// (int) 30 
```
Jika paramater tahun kosong, maka tahun sekarang yang digunakan.


### local_to_gmt

Mengambil input waktu timestamp UNIX dan mengembalikanya ke dalam bentuk GMT.

```php
local_to_gmt(time());

// (int) 1555990937
```

### gmt_to_local

Menkonversi waktu timestamp UNIX ke format GMT yang di alokasikan ke dalam bentuk zona waktu.

```php
$timestamp = 1140153693;
$timezone  = 'UM8';
$daylight_saving = TRUE;
gmt_to_local($timestamp, $timezone, $daylight_saving);

// (int) 1140128493
```

### mysql_to_unix

Mengambil timestamp MySQL sebagai input dan megembalikannya dalam bentuk UNIX timestamp


```php
mysql_to_unix('20061124092345');

// (int) 1164335025
```

### unix_to_human

Mengambil timestamp UNIX sebagai inut dan mengembalikan dalam bentuk format waktu yang bisa di baca oleh manusia dengan prototype sebagai berikut ini

```
YYYY-MM-DD HH:MM:SS AM/PM
```

Hal ini akan sangat berguna jika Anda ingin menampilkan data dalam bentuk form untuk sebuah pengiriman.

Waktu bisa di format dengan atau tanpa detik, dan dapat di ataus ke format Waktu Eropa maupun AS.  Jika timestamp di kirimkan. waktu akan di kembalikan tanpa embel detik dan dalam format AS.


```php
$now = time();
echo unix_to_human($now); // U.S. time, no seconds
echo unix_to_human($now, TRUE, 'us'); // U.S. time with seconds
echo unix_to_human($now, TRUE, 'eu'); // Euro time with seconds

// 2019-04-23 05:44 PM
// 2019-04-23 05:44:53 PM 
// 2019-04-23 17:45:10
```

### human_to_unix

Kebalikan dari fungsi `unix_to_human()`. Fungsi ini mengambil waktu "manusia" ke dllaman  bentuk timestamp UNIX.

```php
$now = time();
$human = unix_to_human($now);
$unix = human_to_unix($human);

// 2019-04-23 05:45 PM
// (int) 1556016360 
```

### nice_date

Fungsi untuk memgambil sebuah format tanggal dalam format buruk dan mengubahnya menjadi format yang baik.

```php
$bad_date = '199605';
// Should Produce: 1996-05-01
$better_date = nice_date($bad_date, 'Y-m-d');

$bad_date = '9-11-2001';
// Should Produce: 2001-09-11
$better_date = nice_date($bad_date, 'Y-m-d');
// 
```

### timezones

Mengmbil referensi zona waktu dan mengembalikannya ke dalam bentuk jam berdasarkan UTC

```php
timezones('UM5');

// (int) -5
```

### date_range_unix


Mencetak daftar tanggal dalam periode tertentu.

```php
date_range_unix('2012-01-01', '2012-01-15')

// Array
// (
//     [0] => 2012-01-01
//     [1] => 2012-01-02
//     [2] => 2012-01-03
//     [3] => 2012-01-04
//     [4] => 2012-01-05
//     [5] => 2012-01-06
//     [6] => 2012-01-07
//     [7] => 2012-01-08
//     [8] => 2012-01-09
//     [9] => 2012-01-10
//     [10] => 2012-01-11
//     [11] => 2012-01-12
//     [12] => 2012-01-13
//     [13] => 2012-01-14
//     [14] => 2012-01-15
// ) 
```


|Time Zone	|Lokasi|
|----|-------|
|UM12	|(UTC - 12:00) Baker/Howland Island
|UM11	|(UTC - 11:00) Samoa Time Zone, Niue
|UM10	|(UTC - 10:00) Hawaii-Aleutian Standard Time, Cook Islands
|UM95	|(UTC - 09:30) Marquesas Islands
|UM9	|(UTC - 09:00) Alaska Standard Time, Gambier Islands
|UM8	|(UTC - 08:00) Pacific Standard Time, Clipperton Island
|UM7	|(UTC - 07:00) Mountain Standard Time
|UM6	|(UTC - 06:00) Central Standard Time
|UM5	|(UTC - 05:00) Eastern Standard Time, Western Caribbean
|UM45	|(UTC - 04:30) Venezuelan Standard Time
|UM4	|(UTC - 04:00) Atlantic Standard Time, Eastern Caribbean
|UM35	|(UTC - 03:30) Newfoundland Standard Time
|UM3	|(UTC - 03:00) Argentina, Brazil, French Guiana, Uruguay
|UM2	|(UTC - 02:00) South Georgia/South Sandwich Islands
|UM1	|(UTC -1:00) Azores, Cape Verde Islands
|UTC	|(UTC) Greenwich Mean Time, Western European Time
|UP1	|(UTC +1:00) Central European Time, West Africa Time
|UP2	|(UTC +2:00) Central Africa Time, Eastern European Time
|UP3	|(UTC +3:00) Moscow Time, East Africa Time
|UP35	|(UTC +3:30) Iran Standard Time
|UP4	|(UTC +4:00) Azerbaijan Standard Time, Samara Time
|UP45	|(UTC +4:30) Afghanistan
|UP5	|(UTC +5:00) Pakistan Standard Time, Yekaterinburg Time
|UP55	|(UTC +5:30) Indian Standard Time, Sri Lanka Time
|UP575	|(UTC +5:45) Nepal Time
|UP6	|(UTC +6:00) Bangladesh Standard Time, Bhutan Time, Omsk Time
|UP65	|(UTC +6:30) Cocos Islands, Myanmar
|UP7	|(UTC +7:00) Krasnoyarsk Time, Cambodia, Laos, Thailand, Vietnam
|UP8	|(UTC +8:00) Australian Western Standard Time, Beijing Time
|UP875	|(UTC +8:45) Australian Central Western Standard Time
|UP9	|(UTC +9:00) Japan Standard Time, Korea Standard Time, Yakutsk
|UP95	|(UTC +9:30) Australian Central Standard Time
|UP10	|(UTC +10:00) Australian Eastern Standard Time, Vladivostok Time
|UP105	|(UTC +10:30) Lord Howe Island
|UP11	|(UTC +11:00) Srednekolymsk Time, Solomon Islands, Vanuatu
|UP115	|(UTC +11:30) Norfolk Island
|UP12	|(UTC +12:00) Fiji, Gilbert Islands, Kamchatka, New Zealand
|UP1275	|(UTC +12:45) Chatham Islands Standard Time
|UP13	|(UTC +13:00) Phoenix Islands Time, Tonga
|UP14	|(UTC +14:00) Line Islands