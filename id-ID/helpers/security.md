# Security

Helper Security berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi Security.
A collection of helper function for security purposes.
## Loading Helper Security

Helper Security dapat di load dengan perintah berikut ini.

```php
$this->load->helper('security');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper Security yang tersedia.


#### strip_image_tags

Fungsi ini merupakan sebuah method security untuk menghapus tag image pada sebuah string dan menyisahkan url gambar sebagai teks biasa.

```php
$source_code = '<img src="https://example.com/image.png">';

strip_image_tags($source_code);

// https://example.com/image.png

```

#### strip_cdata

Mengeluarkan semua enkapsulasi CDATA dari string kode sumber HTML.

```php
$source_code = '<script type="text/javascript">
    //<![CDATA[
    var l=new Array();
    
    //]]>
</script>';
strip_cdata($source_code);

// <script type="text/javascript">
//     //
//     var l=new Array();
    
//     //
// </script> 
```


#### strips_all_tags

Mengeluarkan semua tag HTML dari string kode sumber HTML tetapi tetap menjaga konten aslinya.

```php
$source_code = "Strip all HTML tags from string of HTML <code>source code</code> but keep safe the <strong>original</strong> content.</p>";
strips_all_tags($source_code);

// Strip all HTML tags from string of HTML source code but keep safe the original content.

```

#### strips_tags

Mengeluarkan semua tag HTML dan kontennya pada konten tag yang di didefiniskan. Menhapus semua konten apapun yang memiliki tag pembuka dan penutup, seperti `<table> <object>` dll.

```php
$source_code = "
"<script src=\"scripts/app.js\"></script>
<h1>Hallo</h1>
";
strips_tags($source_code, $disallowed_tags = 'script|style|noframes|select|option', $allowed_tags = '');

// Hallo 
```

#### strip_word_doc

Membuang semua tag kata doc dari string kode sumber.

```php
$source_code = "";
strip_word_doc($source_code, $allowed_tags = '')
// 
```

#### strip_slashes_recursive

Menhapus semua garis miring terbalik.

```php
$string = "\\ \ Who are you\ ";
strip_slashes_recursive($string)

// Who are you 
```


#### strip_comments

Memghapus semua komentar html.

```php
$source_code ="<!--- this comment --->
<p>this paragraf</p>";
strip_comments($source_code)

//  <p>this paragraf</p>
```

#### clean_white_space

Menghapus karakter spasi dari sebuah string yang terkandung.

```php
$source_code = "Hello &nbsp; \n \r World";
clean_white_space($source_code);

// Hello World
```

#### encode_php_tags

Menyadikan tag kode PHP ke dalam entitas.

```php
$string = "";
encode_php_tags($string)
// &lt;?= echo('Hello world') ?&gt;
```

#### escape_html

Memgembalikan semua tag HTML menjadi variable.

```php
$source_code = "<div>Hello World</div>";
escape_html($source_code, $encoding = 'UTF-8', $double_encode = true);

// &lt;div&gt;Hallo, world&lt;/div&gt; 
```
