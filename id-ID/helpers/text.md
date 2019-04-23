
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

Membagi text menjadi array tampa kehilangan kata tersebut.

#### text_columns

Membagi satu blok string atau teks secara merata di pada sejumlah kolom.

#### text_wrap

Membungkus teks pada jumlah karakter yang ditentukan sambil mempertahankan kata-kata lengkap.

#### text_trim

Memotong string yang diberikan hingga panjang tertentu tanpa melanggar sepatah kata pun.

#### text_word_limiter

Membatasi string hingga X jumlah kata.

#### text_character_limiter

Membatasi string berdasarkan jumlah karakter. Mempertahankan kata lengkap sehingga jumlah karakter mungkin tidak persis seperti yang ditentukan.

#### text_censored

Menganti string dan sederet kata yang tidak diizinkan dan apa pun kata-kata yang cocok akan dikonversi ke `####` atau ke pengganti kata yang telah Anda kirim.

#### text_highlight_phrase

Menyorot sebuah frasa dalam string teks.

#### text_word_wrap

membungkus teks dengan karakter yang ditentukan. Menjaga integritas kata-kata.
Apa pun yang ditempatkan di antara {unwrap} {/ unwrap} tidak akan dibungkus dengan kata, juga URL.

#### text_ellipsis
#### text_excerpt
