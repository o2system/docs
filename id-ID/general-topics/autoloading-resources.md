# Autoloading Resource

O2system hadir dengan fitur "Auto-load" yang memungkinkan library, helper, dan model diinisialisasi secara otomatis setiap kali sistem berjalan. Jika Anda membutuhkan resource tertentu secara global di seluruh aplikasi Anda, Anda harus mempertimbangkan memuatnya secara otomatis untuk kelancaran aplikasi Anda.

Item berikut ini dimuat secara otomatis.

- Class yang ditemukan di direktory Library.
- File Helper yand ada di direktoi Helpers
- File konfigarasi khusus yanng ada di direktori Config
- File language yang ada di direktori Languages
- Model yang ditemukan di folder Models.


Untuk memuat resource secara otomatis, buka file `App/Config/Services.php` dan tambahkan item yang ingin Anda muat ke array pengisian otomatis. Anda akan menemukan instruksi dalam file yang sesuai dengan setiap jenis item.

```php

/*
| -------------------------------------------------------------------
|  Autoload Services
| -------------------------------------------------------------------
| These are the classes located in the modular Libraries folder
| or dependency classes located in the composer vendor folder.
| The array key is the offset of the library class.
|
| Example lazy init libraries
|	$services[ 'foo' ] = 'App\Libraries\Foo';
|
| Example init libraries
|   $services[ 'foo' ] = new App\Libraries\Foo( 'bar' );
|
*/

$services['user'] = \O2System\Framework\Libraries\AccessControl\User::class;
```