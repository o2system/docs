
### Text

Helper Text berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi Text.

## Loading Helper Text

Helper Text dapat di load dengan perintah berikut ini.

```php
$this->load->helper('text');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Text yang tersedia.

#### text_split

Membagi teks menjadi array tanpa kehilangan kata-kata.

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et.
<---text-split--->
Irure anim culpa incididunt dolore nulla culpa qui qui occaecat nostrud nisi excepteur proident esse.
<---text-split--->
Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
text_split($text);



// "Eiusmod nostrud in velit tempor laboris dolor pariatur et.
// 
// Irure anim culpa incididunt dolore nulla culpa qui qui occaecat nostrud nisi excepteur proident esse.
// 
// Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
```
Membagi text menjadi array tampa kehilangan kata tersebut.

#### text_columns

Membagi satu blok string atau teks secara merata di pada sejumlah kolom.

```php
$text = "Ut cillum enim dolor sit incididunt deserunt qui incididunt ullamco commodo ad proident esse eu duis elit.";
$cols = 3;
text_columns($text, $cols);

// Array
// (
//     [0] => Ut cillum enim dolor sit incididunt
//     [1] => deserunt qui incididunt ullamco
//     [2] => commodo ad proident esse eu duis elit.
// )
```


#### text_wrap

Membungkus teks pada jumlah karakter yang ditentukan sambil mempertahankan kata-kata lengkap.

```php
$text = "Ut cillum enim dolor sit incididunt deserunt qui incididunt ullamco commodo ad proident esse eu duis elit.";
text_wrap($text);

// Ut cillum
// enim dolor
// sit
// incididunt
// deserunt
// qui
// incididunt
// ullamco
// commodo ad
// proident
// esse eu
// duis elit.
```


#### text_trim

Memotong string yang diberikan hingga panjang tertentu tanpa melanggar sepatah kata pun.

```php
$text = "Ut cillum enim dolor sit incididunt deserunt qui incididunt ullamco commodo ad proident esse eu duis elit. Enim duis irure deserunt irure. Dolor commodo ullamco deserunt adipisicing pariatur est eiusmod reprehenderit voluptate laboris ut et. Cupidatat ut consectetur consequat ea Lorem tempor occaecat incididunt ex consequat nisi proident ipsum ea. In tempor enim Lorem dolor anim dolore ea fugiat Lorem magna id proident irure ea. Duis mollit qui duis duis in nisi pariatur ullamco tempor aliqua elit in eiusmod.";
$limit = 10;
text_trim($text, $limit)

//Eiusmod nostrud in velit tempor laboris dolor pariatur et. 
```


#### text_word_limiter

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et.
Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
$limit = 3;

text_word_limiter($text, $limit)
// Eiusmod nostrud in&#8230;
```
Membatasi string hingga X jumlah kata.

#### text_character_limiter

Membatasi string berdasarkan jumlah karakter. Mempertahankan kata lengkap sehingga jumlah karakter mungkin tidak persis seperti yang ditentukan.


```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et.
Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
$n = 3;
text_character_limiter($text, $n)

// Eiusmod&#8230;
```

#### text_censored

```php
text_censored($text, $replacement)
// 
```
Menganti string dan sederet kata yang tidak diizinkan dan apa pun kata-kata yang cocok akan dikonversi ke `####` atau ke pengganti kata yang telah Anda kirim.

```php

// 
```
#### text_highlight_phrase

Menyorot sebuah frasa dalam string teks.

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et. Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
$text_highlight_phrase = "dolor";
text_highlight_phrase($text, $text_highlight_phrase);

// Eiusmod nostrud in velit tempor laboris <mark>dolor</mark> pariatur et. Nisi officia <mark>dolor</mark> ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.

```
#### text_word_wrap

membungkus teks dengan karakter yang ditentukan. Menjaga integritas kata-kata.
Apa pun yang ditempatkan di antara {unwrap} {/ unwrap} tidak akan dibungkus dengan kata, juga URL.

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et. Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
text_word_wrap($text);

// Eiusmod nostrud in velit tempor laboris dolor pariatur et. Nisi officia
// dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam
// quis esse ad veniam in irure.
```
#### text_ellipsis

Fungsi ini akan menghapus tag dari string, membaginya di max_length dan ellipsis

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et. Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
ext_ellipsis($text, $max_length);

// Eiusmod no&hellip;
```
#### text_excerpt

Memungkinkan untuk mengekstrak sepotong teks yang mengelilingi kata atau frasa.

```php
$text = "Eiusmod nostrud in velit tempor laboris dolor pariatur et. Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam quis esse ad veniam in irure.";
text_excerpt($text);

//  Eiusmod nostrud in velit tempor laboris dolor pari  tur et. Nisi officia dolor ullamco reprehenderit adipisicing consectetur ea eu ea aliqua veniam ...
```