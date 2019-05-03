# Middleware

Middleware menyediakan mekanisme untuk memfilter permintaan HTTP memasuki aplikasi Anda. Misalnya, O2System menyertakan middleware yang memverifikasi bahwa pengguna aplikasi Anda diautentikasi. Jika pengguna tidak diautentikasi, middleware akan mengarahkan pengguna ke layar login. Namun, jika pengguna diautentikasi, middleware akan memungkinkan permintaan untuk melanjutkan lebih jauh ke dalam aplikasi.

Middleware tambahan dapat ditulis untuk melakukan berbagai tugas selain otentikasi. Middleware CORS mungkin bertanggung jawab untuk menambahkan tajuk yang tepat untuk semua tanggapan yang meninggalkan aplikasi Anda. Middleware logging mungkin mencatat semua permintaan yang masuk ke aplikasi Anda.

Ada beberapa middleware yang termasuk dalam kerangka O2System, termasuk middleware untuk otentikasi dan perlindungan CSRF. Semua middleware ini terletak di direktori `app / Http / Middleware`.


## Mendefinisikan Middleware

Untuk membuat middleware baru, gunakan perintah `make: middleware` Artisan:

    php artisan make: middleware CheckAge

Perintah ini akan menempatkan kelas `CheckAge` baru di dalam direktori` app / Http / Middleware` Anda. Di middleware ini, kami hanya akan mengizinkan akses ke rute jika `usia` yang disediakan lebih besar dari 200. Jika tidak, kami akan mengarahkan pengguna kembali ke URI` rumah`:

```php
 <?php
namespace App\Http\Middleware;

// ------------------------------------------------------------------------

use Psr\Http\Server\RequestHandlerInterface;
use Psr\Http\Message\ServerRequestInterface;
use Psr\Http\Message\ResponseInterface;

/**
 * Class Throttle
 * @package App\Http\Middleware
 */
class Throttle implements RequestHandlerInterface
{
    /**
     * Throttle::handle
     *
     * Handles a request and produces a response
     *
     * May call other collaborating code to generate the response.
     *
     * @param ServerRequestInterface $request
     *
     * @return ResponseInterface
     */
    public function handle(ServerRequestInterface $request): ResponseInterface
    {
        services()->throttle->request($request);
        services()->throttle->rate([
            'span' => 1,
            'retry' => 10,
            'attempts' => 5,
        ]);

        if( ! services()->throttle->verify()) {
            output()->sendError(429);
        }
    }
}
```
