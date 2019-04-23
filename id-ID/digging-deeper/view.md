View adalah sebuah file yang bertugas untuk menampilkan output dari semua proses yang sudah dilakukan pada bagian controller dan model.

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


Untuk bisa digunakan di dalam aplikasi, file view harus di-load di dalam method controller. Berikut adalah contoh me-load file view di dalam method index pada controller home.


```php
<?php
namespace App\Controllers;
use App\Http\Controller;

class Home extends Controller {
    
    public function index(){
        
        view('helloworld');
    }
}
```

Untuk menampilkan data output dari controller ke view, maka masing-masing data tersebut harus di isikan ke sebuah variable array. Nilai yang diisikan bisa data apapun, array, object, string, integer, boolean dll.

Berikut adalah contoh untuk meneruskan data yang diproduksi di controller dan menampilkannya di view:

```php
public function index($param = null)
{
    $name = 'Jone Doe';

    // CI Style
    $this->load->view('tutorial', ['name' => $name]);	
    
    // Laravel & CI4 Style
    view('tutorial',['name' => $name]);
}
```
