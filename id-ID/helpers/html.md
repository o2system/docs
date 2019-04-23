
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
