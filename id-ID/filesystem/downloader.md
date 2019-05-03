# Downloader

O2System Files class memungkinkan sebuah file dapat di unduh dari server dengan prefereces yang di inginkan.

```php
use O2System\Filesystem\Files;

// Write a CSV file example
$csvFile = new Files\CsvFile();
$csvFile->createFile( 'path/to/files/filename.csv' );
$csvFile->store( 'foo', 'bar' );
$csvFile->writeFile();

// File download handler
$downloader = new Handlers\Downloader( 'path/to/files/downloadthis.zip' );
$downloader
    ->speedLimit( 1024 )
    ->resumeable( true );

// Send the requested download file
$downloader->download();
```