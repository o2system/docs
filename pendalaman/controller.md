# Controller

Dalam mengembangkan aplikasi dengan Design Pattern HMVC, controller berperan untuk mengarahkan setiap request ke aplikasi. Controller umumnya digunakan untuk menjawab request yang dikirim ke route, yang selanjutnya akan diarahkan ke model yang diperlukan.
Dengan pemahaman ini, sebaiknya sebuah controller emang memiliki sedikit kode. Sementara model memiliki banyak kode, karena di model-lah business logic dari aplikasi akan berjalan. Teknik sedikit code di controller dan banyak kode di model ini biasa dikenal dengan istilah thick model, thin controller. Dan ini merupakan best practices yang bisa kita jadikan pegangan selama koding.

## Membuat sebuah Controller

Untuk membuat sebuah comtroller di O2system cukuplah mudah hanya dengan membuat sebuah class di folder `app/Controller`. nama controller sebaiknya di smaakan dnegan model yang di buat.

```php
<?php

namespace App\Controllers;

use App\Http\Controller;
class Geodirectory extends Controller
{
    
}
```

##