
# Inflector

Helper Inflector berisi beberapa fungsi yang memunngkinkan anda untuk mengatur/memanipulasi string, seperti mengubah kata tunggal menjadi jamak atau sebalikanya.


## Loading Helper Array

Helper Array dapat di load dengan perintah berikut ini.

```php
$this->load->helper('inflector');
```


## Fungsi yang tersedia

Berikut ini merupakan beberapa helper common yang tersedia.

### readable


```php

```

### singular

Method `singular()` mengkoversi string ke dalam bentuk tunggal. Fungsi ini hanya mendukung bahasa inggris.

```php
singular('books');

// book

singular('children');

// child
```

### plural

method `plural()` mengkonversi string ke dalam bentuk jamak. Fungsi ini hanya mendukung dalam bahasa inggris.

```php
plural('book');

// books

```

### studlycase

Method studlycase mengubah string menjadi huruf besar/kecil

```php
studlycase('books');

// Books

studlycase('Books');

// books
```

### camelcase

Method untuk mengubah string yang di pisah dengan garis bawah atau spasi menjadi dalam bentuk cameCase

```php
camelcase('books_store');
camelcase('books store');

// booksStore
```

### snakecase

Fungsi untuk mengkonversi string camelCase ke dalam snake_case.

```php
snakecase('books Store');

// books_store
```

### underscore

Fungsi untuk menggabungkan beberapa kata dengan menggunakan garis bawah.

```php
underscore('hello world');

// hello_world
```

### dash

Fungsi untuk menhasilkan url friendly dengan menambahkan `-` pada sebuah string.

```php
dash('hello world');

// hello-world
```

### is_countable

Fungsi untuk mengecek apakah string bisa di hitung.

```php
is_countable('hello world');

// (bool) TRUE
```
