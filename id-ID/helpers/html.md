
# Html
Helper HTML berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi tag HTML.

## Loading Helper HTML

Helper HTML dapat di load dengan perintah berikut ini.

```php
$this->load->helper('html');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper html yang tersedia.

### tag

```php
$tagName = 'label';
$content = 'title';
$attributes = array('for' => 'title', 'class' => 'control-label');

tag($tagName, $contents, $attributes)

// <label for="title" class="control-label">Title </label> 
```

### video

```php
$src = 'video.mp4';
video($src)

// <video width="320" height="240" controls> VIDEO_NOT_SUPPORTED </video>
```

### audio

```php
$src = 'audio.mp3';
audio($src, array $attributes = [])

// <audio controls>
// AUDIO_NOT_SUPPORTED
// </audio> 
```

### canvas

```php

canvas($attributes)

// <canvas>
// CANVAS_NOT_SUPPORTED
// </canvas> 
```

### heading

Fungsi untuk membuat seubuah tag heading, diaman paramater pertama berisi data sedangakan paramater kedia adalah ukurang heding.

```php
heading('Welcome!', 3);

// <h3>Welcome!</h3>
```

Selain itu utnuk menambahkan attribut tke htag heading seperti class, id, attribute html gunakan paramater ketiga seperti berikut ini.

```php
heading('Welcome!', 3, 'class="pink"');
heading('How are you?', 4, array('id' => 'question', 'class' => 'green'));

// <h3 class="pink">Welcome!<h3>
// <h4 id="question" class="green">How are you?</h4>
```

### ul

```php
$list = array('Merah', 'kuning', 'Biru', 'Hitam', 'Putih' );
$attributes = array('class' => 'list-style');
ul($list, $attributes)

// 
```

### ol

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

### img

Fungsi untuk membuat sebuah tag html `<img />`. Paramater pertama berisi sumber gambar.

```php
img('images/picture.jpg'); 

// <img src="http://site.com/images/picture.jpg" />
```

Ada parameter kedua yang bersifat opsional yang merupakan nilai boolean 

### meta

```php
$meta = 'generator';
$content = 'O2CMS - Liquid Content Management System';
$type = 'name';

meta($meta, $content, $type)
// <meta name="generator" content="O2CMS - Liquid Content Management System">
```

### parse_attributes

```php
parse_attributes($string)
// 
```

### remove_tags

```php
$html = "<div> Anim pariatur cliche reprehenderit.</div>";
$tags = 'div';
remove_tags($html, $tags)

// Anim pariatur cliche reprehenderit.
```

### extract_tag

```php

$html = "<div> Anim pariatur cliche reprehenderit.</div>";
$tags = 'div';
extract_tag($html, $tag = 'div')

// Anim pariatur cliche reprehenderit.
```
