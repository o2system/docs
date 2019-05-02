# RelationShips

## Pengenalan

Sebuah tabel database sering kali berhubunguan dengan database lainya satu sama lain. Sebagai contoh adalah tabel post pada blog yang berelasi dengan dengan komentar, kategori, tag dll. ORM O2system memudahkan mengelola tabel dengan mudah untuk menghububngkan tabel-table tersebut.

## Definisi Relationships

### One To One


Relasi database one-to-one sering juga disebut dengan relasi dasar. Sebagai contoh, model User memiliki satu table telepon. Untuk medefinisikan tabel relasi ini. Kita akan menempatkan method phone pada class model User.

```php
class User extends Model;
{
    public function phone()
    {
        return $this->hasOne('App\Models\Phone', 'foreign_key');
    }
}
```

Argumen pertama yang diteruskan ke method `hasOne` adalah nama model terkait. setelah relasi di definisikan, maka ORM O2Ssytem akan memgaitkan model tersebut secara dinamis.

Jika pada contoh di atas kita bisa menakses model `Phone` dari model `User`. Maka di sini kita akan mengakses model `User` dari model `Phone`. Kita sebut motede ini adalah metode kebalikan dari relasi `hasOne` menggunakan method `belongsTo`.

```php
class Phone extends Model
{
    public function user()
    {
        return $this->belongsTo('App\Models\User', 'foreign_key');
    }
}
```

Pada contoh diatas ORM O2System akan memcocokan `foreign_key` pada model `Phone` ke model `User`. ORM O2system menentukan relasi antar model dengan memggunakan `foreign_key`.


```php
/**
 * Get the user that owns the phone.
 */
public function user()
{
    return $this->belongsTo('App\Models\User', 'foreign_key');
}
```

### One To Many

Relasi `one-to-many` digunakan utuk mementukan hubungan dimana model tunggal memiliki banyak hubungan relasi. sebagai contoh, database blog memiliki beberapa komentar. Seperti ORM pada umumnya relasi one-to-many di definiskan dengan menepatkan fungsi pada model Anda.


```php
class Post extends Model
{
    /**
     * Get the comments for the blog post.
     */
    public function comments()
    {
        return $this->hasMany('App\Models\Comment', 'foreign_key');
    }
}
```

Setelah relasi di hubungkan dengan benar. kita dapat mengakses komentar dengan cara mengakses properti komentar tersebut seperti contoh berikut ini.

```php
$model = App\Models\Post::class;

$comments = $this->model->comments;

foreach ($comments as $comment) {
    //
}
```

### One To Many(Inverse)

Lalu gimanan kalau ingin mengakses semua post dari sebuah komentar. UNtuk mendefinisikan inverse one-to-many maka gunakan fungsi `belongsTo` pada model yang digunakan.

```php
class Comment extends Model
{
    /**
     * Get the post that owns the comment.
     */
    public function post()
    {
        return $this->belongsTo('App\Models\Post', 'foreign_key');
    }
}
```

Setelah relasi di definisikan, kita dapat mengambi model Post dari komentar dengan mengaksei propertiny sepertib berikut ini.

```php
$comment = models('App\Models\Post')->find(1);

echo $comment->post->title;
```

Pada contoh  diatas, ORM O2system akan memcocokan nilai `foreign_key` dari model Comment ke kolom id pada model Post.

### Many To Many

Relasi many-to-many sedikit lebih sulit daripada hasOne atau HasMany. Contoh hubungan seperti ini adalah sebuah post blog yang memiliki banyak tag dan sebaliknya tag yang memiliki banyak post.

Relasi many-to-many di definisikan dengan dengan menulis metode yang mengembalikan hasil ke method belongsToMany.

```php

class Post extends Model
{
    public function tag()
    {
        return $this->belongsToMany('App\Models\Tag', 'id_tag');
    }
}
```

Setelah relasi di definisikan. Anda dapat mengakses semua tag post dengan menggunakan properti yang dinamis seperti berikut ini.

```php
$user = models('App\Models\Post')->find(1);

foreach ($post->tags as $tag) {
    //
}
```

Untuk mendefinisikan invers dari many-to-many Anda bisa menggunakan fungsi `belongsToMany` pada model yang terkait seperti berikut ini.


```php

class Tag extends Model
{
    public function post()
    {
        return $this->belongsToMany('App\Models\Post', 'id_post');
    }
}
```

Seperti yang Anda lihat, relasi invers one-to-many didefinisikan persis seperti one-to-many seperti biasa. hanya saja dengan model referensi yang berbeda(berbalik). Karena kita meggnuakan `belongsToMany`.

### Has One Through

Rrelasi has-one-through memghubungkan model melalui sebuah relasi perantara tunggal. Misalnya jika model Suplier memiliki satu pengguna di model User dan setiap pengguna di kaitakan dengan riwayat pengguna (model History) maka model suplier dapat mengakses  model History User melalui model User. Untuk lebih jelasnya perhatikan contoh berikut ini.

```
users
    id - integer
    id_supplier - integer

suppliers
    id - integer

history
    id - integer
    id_user - integer
```

Meskipun tabel hostory tidak mengandung kolom `id_supplier` relasi `hasOneThrough` bisa menyediakan akses ke riwayat pengguna melalui model Supplier. Sebagai contoh dalam definisi diatas maka maka perhatikan model di bawah ini.

```php
class Supplier extends Model
{
    /**
     * Get the user's history.
     */
    public function userHistory()
    {
        return $this->hasOneThrough('App\Models\History', 'App\Models\User');
    }
}
```

Argumen pertama yang di diteruskan ke motode `hasOneThrough` adalah nama model akhir yang ingin kita akses. sendangkan argumen kedua adalah nama model perantara.

### Self Referencing Relationship

Terkadang kita membutuhkan sebuah model berelasi ke dirinya sendiri. Contohya relasi antara
departemen dan sub departement. Keduanya merupakan model departement.

Untuk membuat relasi seperti ini, kita harus menambah field khusus misalnya `id_parent` yang akan digunakan untuk menentukan department dan sub department.

Kita juga harus menggunakan relasi `belongsTo` (untuk menentukan department) dan hasMany (untuk
menentukan sub department). Tentunya, kita juga pada kedua method ini, kita harus menambah field `id_parent` sebagai custom foreign key.

Hasil akhir modelnya akan seperti berikut:

```php
class Department extends Model {

public function parent()
{
    return $this->belongsTo('App\Models\Department', 'id_parent');
}
public function childs()
{
    return $this->hasMany('App\Models\Department', 'id_partment');
}
}
```