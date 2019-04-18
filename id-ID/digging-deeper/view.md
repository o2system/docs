## Membuaut View

Untuk membuat view, kita dapat membuat file baru di dalam folder `resources/views` dengan extensi .phtml. Misalnya kita buat view untuk menampilkan kalimat hello dengan nama view
hello.phtml:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Hello World</title>
</head>
<body>
<h1>Hello World</h1>
<p>
This is hallo world
</p>
</body>
</html>
```

Terlihat disini, kita menggunakan html biasa pada view ini. Untuk menampilkan view ini, kita dapat
menggunakan method  `view('nama-view')`. Misalnya, kita buat route /hello untuk
menampilkannya.