Presenter adalah kelas yang berisi logika yang diperlukan untuk menghasilkan tampilan (atau view) Anda. Ketika controller dilakukan dengan input pengguna Anda dan dilakukan dengan tindakan apa pun yang diperlukan untuk mengambil, itu mengalihkan eksekusi ke Presenter untuk mengambil dan memproses data apa pun yang diperlukan untuk tampilan. Presenter tidak boleh melakukan manipulasi data apa pun tetapi dapat berisi panggilan basis data dan operasi pengambilan atau persiapan lainnya yang diperlukan untuk menghasilkan data Tampilan.

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