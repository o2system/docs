
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
