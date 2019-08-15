# Presenter

Presenter merupakan class PHP yang berisi logika yang diperlukan untuk menghasilkan view. Ketika pengendali dilakukan dengan masukan pengguna Anda dan dilakukan dengan tindakan apa pun yang diperlukan untuk dilakukan, ternyata eksekusi ke Presenter untuk mengambil dan memproses data apa pun yang diperlukan untuk tampilan tersebut. Presenter tidak boleh melakukan manipulasi data apapun namun dapat berisi panggilan database dan operasi pengambilan atau persiapan lainnya yang diperlukan untuk menghasilkan data View.

```php
<?php

namespace App\Http;

class Presenter extends \O2System\Framework\Http\Presenter
{
    public function __construct()
    {
        parent::__construct();

        $this->meta->title->prepend('O2System Framework');
    }
}
```

