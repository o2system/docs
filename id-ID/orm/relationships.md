# RelationShips

## Pengenalan

Sebuah tabel database sering kali berhubunguan dengan database lainya satu sama lain. Sebagai contoh adalah tabel post pada blog yang berelasi dengan dengan komentar, kategori, tag dll. ORM O2system memudahkan mengelola tabel dengan mudah untuk menghububngkan tabel-table tersebut.

## Definisi Relationships


```php
$user->posts()->where('active', 1)->get();
```
### One To One


Relasi database one-to-one sering juga disebut dengan relasi dasar. Sebagai contoh, model User memiliki satu table telepon. Untuk medefinisikan tabel relasi ini. Kita akan menempatkan method phone pada class model User.

```php
class User extends Model;
{
    public function phone()
    {
        return $this->hasOne('App\Models\Phone');
    }
}
```

Argumen pertama yang diteruskan untuk memangig

O2system ORM menggunakan 

```php
return $this->hasOne('App\Models\Phone', 'foreign_key');
```

```php
class Phone extends Model
{
    public function user()
    {
        return $this->belongsTo('App\Models\User');
    }
}
```

```php
/**
 * Get the user that owns the phone.
 */
public function user()
{
    return $this->belongsTo('App\Models\User', 'foreign_key');
}
```

```php
/**
 * Get the user that owns the phone.
 */
public function user()
{
    return $this->belongsTo('App\Models\User', 'foreign_key', 'other_key');
}
```

### One To Many

Relasi one-to-many digunakan utuk mementukan hubungan dimana model tunggal memiliki banyak hubungan relasi. sebagai contoh, database blog memiliki beberapa komentar.


```php
/**
 * Get the user that owns the phone.
 */
public function user()
{
    return $this->belongsTo('App\Models\User', 'foreign_key', 'other_key');
}
```

### One To Many(Inverse)

```php
class Comment extends Model
{
    /**
     * Get the post that owns the comment.
     */
    public function post()
    {
        return $this->belongsTo('App\Post');
    }
}
```

### Many To Many


