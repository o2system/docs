# Instalasi


## Kebutuhan Server

Untuk mulai bekerja dengan O2System Framework anda harus memastikan server anda telah memenuhi persyaratan minimum berikut:

- PHP >= 7.2
- Fileinfo
- Mcrypt
- OpenSSL
- Mbstring
- Tokenizer
- XML
- APCu & Zend OPCache

## Instalasi

### Instalasi via Composer

O2System Framework menggunakan [Composer](https://getcomposer.org/download/) sebagai Dependency Management, jadi langkah termudah untuk melakukan instalasi adalah dengan menggunakan perintah  berikut ini:

```bash
composer create-project o2system/o2system [project-name]
```

### Verifikasi Instalasi

Seteleah instalasi selesai, cek aplikasi telah berjalan dengan perintah [bawaan php web server](https://secure.php.net/manual/en/features.commandline.webserver.php) dengan menjalankan peerintah berikut ini di console.

```bash
php o2system serve

```

## Konfigurasi

### Direktori public


Setelah pemasangan O2ystem selesai, Anda harus memastikan bahwa konfigurasi web server/webroot mengarah ke direktori `public`. file `index.php` pada direktori tersebut merupakan front controller/bootstraping dari semua request HTTP.

### File Konfigurasi

Semua file konfigurasi O2system terletak di direktori app/Config. semua pilihan kofigurasi telah terdokumentasi dengan baik di dalam file tersebut. Anda bisa mencoba beberapa konfigurasi yang di perlukan.

### diretori permisi

Setelah selesai melakukan instalasi O2System Framework anda wajib memastikan bahwa direktori `cache` dan `storage` dapat ditulis oleh aplikasi anda.

Mengubah permission pada direktori cache

```bash
$ chmod -R 777 /path/to/your/project/cache
```

Mengubah permission pada direktori storage

```bash
$ chmod -R 777 /path/to/your/project/storage
```

## Konfigurasi Web Server

### Apache

O2system telah menyertakan konfigurasi awal file `public/.httaccess` untuk membuat sebuah url tanpa index.php pada path front controller. Sebelum menjalankan server apache, pastikan terlebih dahulu untuk mengaktikan module apache `mod_rewrite` pada `.htaccess`.



```conf
# ----------------------------------------------------------------------
# UTF-8 encoding
# ----------------------------------------------------------------------

# Use UTF-8 encoding for anything served text/plain or text/html
AddDefaultCharset utf-8

# Force UTF-8 for a number of file formats
<IfModule mod_mime.c>
    AddCharset utf-8 .atom .css .js .json .rss .vtt .xml
</IfModule>

# ----------------------------------------------------------------------
# Rewrite engine
# ----------------------------------------------------------------------

# Turning on the rewrite engine is necessary for the following rules and features.
# FollowSymLinks must be enabled for this to work.
<IfModule mod_rewrite.c>
    <IfModule mod_negotiation.c>
        Options -MultiViews
    </IfModule>

    Options +FollowSymlinks -Indexes
    RewriteEngine On

    # If you installed O2System in a subfolder, you will need to
    # change the following line to match the subfolder you need.
    # http://httpd.apache.org/docs/current/mod/mod_rewrite.html#rewritebase
    # RewriteBase /

    # Rewrite "www.example.com -> example.com"
    RewriteCond %{HTTPS} !=on
    RewriteCond %{HTTP_HOST} ^www\.(.+)$ [NC]
    RewriteRule ^ http://%1%{REQUEST_URI} [R=301,L]

    # Handle Front Controller...
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.php [QSA,L]

    # Handle Authorization Header
    RewriteCond %{HTTP:Authorization} .
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
</IfModule>

# ----------------------------------------------------------------------
# Gzip compression
# ----------------------------------------------------------------------

<IfModule mod_deflate.c>

	# Force deflate for mangled headers developer.yahoo.com/blogs/ydn/posts/2010/12/pushing-beyond-gzipping/
	<IfModule mod_setenvif.c>
		<IfModule mod_headers.c>
			SetEnvIfNoCase ^(Accept-EncodXng|X-cept-Encoding|X{15}|~{15}|-{15})$ ^((gzip|deflate)\s*,?\s*)+|[X~-]{4,13}$ HAVE_Accept-Encoding
			RequestHeader append Accept-Encoding "gzip,deflate" env=HAVE_Accept-Encoding
		</IfModule>
	</IfModule>

	# Compress all output labeled with one of the following MIME-types
	# (for Apache versions below 2.3.7, you don't need to enable `mod_filter`
	# and can remove the `<IfModule mod_filter.c>` and `</IfModule>` lines as
	# `AddOutputFilterByType` is still in the core directives)
	<IfModule mod_filter.c>
		AddOutputFilterByType DEFLATE application/atom+xml \
		                              application/javascript \
		                              application/json \
		                              application/rss+xml \
		                              application/vnd.ms-fontobject \
		                              application/x-font-ttf \
		                              application/xhtml+xml \
		                              application/xml \
		                              font/opentype \
		                              image/svg+xml \
		                              image/x-icon \
		                              text/css \
		                              text/html \
		                              text/plain \
		                              text/x-component \
		                              text/xml
    </IfModule>
</IfModule>

```

### NGINX

Bagi anda yang menggunakan NGINX sebagai web-server, buatlah vhost untuk proyek aplikasi anda lalu isi file vhost tersebut dengan konfigurasi seperti contoh di bawah ini.

```conf
server {
        listen *:80;
        server_name example.com *.example.com;

        root  /path/to/your/project/public;
        index  index.html index.htm index.php;

        charset utf-8;

        location / {
                try_files $uri $uri/ /index.php$is_args$args;
        }

        location = /favicon.ico { access_log off; log_not_found off; }
        location = /robots.txt  { access_log off; log_not_found off; }

        access_log off;
        error_log  /path/to/your/nginx/logs/example.com.error.log;

        location ~ \.php$ {
                fastcgi_split_path_info ^(.+\.php)(/.+)$;
                
                # fastcgi_pass unix:/var/run/php-fpm.sock;
                fastcgi_pass 127.0.0.1:9000;
                
                fastcgi_index index.php;
                include fastcgi_params;
                fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
                fastcgi_intercept_errors off;
                fastcgi_buffer_size 16k;
                fastcgi_buffers 4 16k;

                include fastcgi_params;
        }

        location ~ /\.ht {
                deny all;
        }
}
```
### Microsoft IIS

Setelah anda memastikan IIS anda sudah memiliki plugin Rewrite Rule, buatlah file web.config di root direktori project anda dan isikan seperti contoh dibawah ini.

```bash
<configuration>
        <system.webServer>
                <rewrite>
                        <rules>
                                <clear />
                                <rule name="REQUEST_URI" stopProcessing="true">
                                        <match url="^" ignoreCase="false" />
                                        <conditions logicalGrouping="MatchAll" trackAllCaptures="false">
                                        <add input="{REQUEST_FILENAME}" matchType="IsDirectory" ignoreCase="false" negate="true" />
                                        <add input="{REQUEST_FILENAME}" matchType="IsFile" ignoreCase="false" negate="true" />
                                        </conditions>
                                        <action type="Rewrite" url="index.php" />
                                </rule>
                        </rules>
                </rewrite>
        </system.webServer>
</configuration>
```