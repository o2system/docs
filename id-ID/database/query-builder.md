# Query Builder

Query Builder membantu Anda untuk membuat query database secara dinamis dengan lebih cepat. Sebagian besar penggunaan method diakses dengan cara Method Chaining.

Untuk menggunakan feature ini pastikan konfigurasi koneksi ke database sudah benar. Untuk detail panduan koneksi database, silahkan klik di halaman [konfigurasi]().

## Beberapa Method Query Builder

### Mengambil semua baris data di Tabel

Ada bisa menggunakan method select() untuk memgambil semau baris data di dalam databases


Untuk mendapatkan data dari semua kolom tabel:

```php
$data = $this->qb->select()->from('users')->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM posts
```


Fungsi SQL juga bisa diisikan pada argument select():

```php
$data = $this->qb->select('COUNT(*)')->from('users')->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT COUNT(*) FROM users
```


### Join

Untuk melakukan query dari beberapa tabel, method join() bisa digunakan.

```php
$data = $this->qb->select('users.name', 'posts.post')->from('users')->join('posts')->on('users.id', '=', 'posts.post_author');
```

Method ini menghasilkan output data SQL:

```sql
SELECT users.name, posts.post FROM users JOIN posts ON 
(users.id = posts.post_author)
```

Anda juga bisa menambahkan tipe join seperti LEFT, RIGHT dan INNER pada argument ke dua di dalam method join().

```php
$data = $this->qb->select('users.name', 'posts.post')->from('users')->join('posts', 'RIGHT')->on('users.id', '=', 'posts.post_author');
```

Method ini menghasilkan output data SQL:

```sql
SELECT users.name, posts.post FROM users RIGHT JOIN posts ON (users.id = posts.post_author)
```

### Where

Untuk membatasi hasil pencarian Anda bisa menggunakan method where().

```php
object where($field, $value = null, $escape = null);
```

Berikut contoh penggunaan method ini:

```php
$data = $this->qb->select()->from('users')->where('id', 1)->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id = 1
```

Jika penyeleksian data lebih dari satu kondisi:

```php
$data = $this->qb->select()->from('users')->where('id', '=', 1, 'OR')->where('email', '=', 'kandar@kandar.com')->get();
```

Penggunaan operator IN:

```php
$data = $this->qb->select()->from('users')->where('id', 'IN', array(1,4,7))->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id IN 1,4,7
```

Penggunaan operator BETWEEN:

```php
$data = $this->qb->select()->from('users')->where('id', 'BETWEEN', array(1,7))->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id BETWEEN 1 AND 7
```

## Group By

Penggunaan method groupBy():

```php
$data = $this->qb->select('id', 'name')->from('users')->groupBy('name', 'id')->limit(10)->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT id, name FROM users GROUP BY name, id LIMIT 10
```
## Having

Berikut adalah contoh cara menggunakan method having():

```php
$data = $this->qb->select('id', 'post_title')->from('posts')->groupBy('post_author','id', 'post_title')->having('COUNT(id)', '>=', 2)->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM posts GROUP BY post_author HAVING COUNT(id) >= 2
```

## Order By

Untuk mengurutkan hasil pencarian data, Anda bisa menggunakan method orderBy()

```php
$data = $this->qb->select()->from('users')->orderBy('id')->get();
Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users ORDER BY id
```

Cara yang lain:

```sql
$data = $this->qb->select()->from('users')->orderBy('id', 'DESC')->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users ORDER BY id DESC
```

Penggunaan dengan method where():

```php
$data = $this->qb->select()->from('users')->where('id', '>', 1)->orderBy('id', 'DESC')->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id > 1 ORDER BY id DESC
```

### Limit

Argument pertama digunakan untuk menentukan jumlah limit. Berikut adalah cara penggunaan method limit():

```php
$data = $this->qb->select()->from('users')->where('id', '>', 1)->orderBy('id', 'DESC')->limit(3)->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id > 1 ORDER BY id DESC LIMIT 3
```

Sedangkan argument ke dua digunakan untuk menentukan nilai offset:

```php
$data = $this->qb->select()->from('users')->where('id', '>', 1)->orderBy('id', 'DESC')->limit(6,2)->get();
```

Method ini menghasilkan output data SQL:

```sql
SELECT * FROM users WHERE id > 1 ORDER BY id DESC LIMIT 6 OFFSET 2
```

### Insert
Untuk menambahkan data baru dengan cara:

```php
$query = $this->qb->insert('table_name', array('name' => 'jhon', 'email' => 'budi@budi.com'));
```

Method ini adalah abstraksi dari SQL:

```sql
INSERT INTO table_name (name, email) VALUES ('jhon', 'budi@budi.com')
```

### Update

Untuk melakukan update record dengan cara:

```php
$query = $this->qb->update('table_name', array('name' => 'jhon gmail', 'email' => 'jhon@gmail.com'), array('id' => 6));
```

Method ini adalah abstraksi dari SQL:

```php
UPDATE table_name SET name = 'budi', email = 'budi@budi.com' WHERE id = 6
```

Kriteria juga bisa di-passing ke dalam method 

```php
$this->qb->where().

$this->qb->where('id', '>', 1, 'AND');
$this->qb->where('id', '<', 10);
$this->qb->update('table_name', array('status' => 'PUBLISH') );
```

Hasil abstraksi SQL:

```php
UPDATE table_name SET status = 'PUBLISH' WHERE id > 1 AND id < 10
```

### Delete

Untuk menghapus record dengan cara:

```php
$query = $this->qb->delete('table_name', array('id' => '6'));
```

Method ini adalah abstraksi dari SQL:

```sql
DELETE FROM table_name WHERE id = 6
```

Atau menggunakan method $this->qb->where().

```php
$this->qb->where('id', '>', 1, 'AND');
$this->qb->where('id', '<', 10);
$this->qb->delete('table_name');
```

Hasil abstraksi SQL:

```sql
DELETE FROM table_name WHERE id > 1 AND id < 10
```