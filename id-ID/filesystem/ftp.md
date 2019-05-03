# FTP

O2System FTP class memungkinkan sebuah file dapat ditransfer ke ke server dengan di remot. File yang di remote dapat id pindahkan, di ganti namanya dan di hapus. Class FTP juga dapat mencakup fungsi "mirroring" yang memungkinkan untuk membuat sebuah direktori lokal yang di buat dengan jarak jauh melalui FTP.

## Bekerja dengan Class FTP

Pada contoh berikut ini koneksi di buka ke server FTP. dan file lokal dibaca dan diunggah ke server dengan permisi file di atur ke 755.

```php
use O2System\Filesystem\Handlers\Ftp;

$ftp = new Ftp();
$config['hostname'] = 'ftp.example.com';
$config['username'] = 'your-username';
$config['password'] = 'your-password';
$config['debug']        = TRUE;

$ftp->connect($config);

$ftp->upload('/local/path/to/myfile.html', '/public_html/myfile.html', 'ascii', 0775);

$ftp->close();

```

Pada contoh ini file di server di ambil ke local.

```php
use O2System\Filesystem\Handlers\Ftp;

$config['hostname'] = 'ftp.example.com';
$config['username'] = 'your-username';
$config['password'] = 'your-password';
$config['debug']        = TRUE;

$ftp->connect($config);

$list = $ftp->list_files('/public_html/');

print_out($list);

$ftp->close();
```

Pada contoh berikut ini direktori lokak di mirror kan ke server.

```php
use O2System\Filesystem\Handlers\Ftp;

$config['hostname'] = 'ftp.example.com';
$config['username'] = 'your-username';
$config['password'] = 'your-password';
$config['debug']        = TRUE;

$ftp->connect($config);

$ftp->mirror('/path/to/myfolder/', '/public_html/myfolder/');

$ftp->close();
```

