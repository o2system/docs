
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
