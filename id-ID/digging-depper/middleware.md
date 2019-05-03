# Middleware

Didalam dunia software engineering middleware merupakan sebuah perangkat lunak perantara yang berada diantara kernel dan aplikasi yang salah satu fungsinya adalah sebagai lapisan penyaring permintaan. Pada aplikasi berbasis web middleware middleware merupakan lapisan penyaring permintaan HTTP. 

## Bagaimana Cara Middleware Bekerja?

Framework yang berbeda menerapkan middleware secara berbeda. O2System Framework menerapkan middleware sebagai lapisan konsentris. Lapisan middleware yang pertama diterapkan akan menjadi lapisan middleware terluar dan akan dijalankan dengan metode FIFO (First In First Out) dimulai dari lapisan terluar hingga lapisan terdalam.

![Middleware](http://www.slimframework.com/docs/v3/images/middleware.png)

## Lapisan Built-In Middleware

O2System Framework sudah menyertakan beberapa mekanisme middleware, antara lain:
- Cache Middleware
- Csrf Middleware
- Environment Middleware
- Maintenance Middleware
- Sign On Middleware

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
