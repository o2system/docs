
# Routing

Dalam membangun website, URL yang mudah diingat itu penting. Selain memudahkan user untuk mengingat alamat web, URL yang deskriptif juga sangat berpengaruh dalam SEO.


O2system menangani perihal URL ini dengan serius. Jika menggunakan PHP native, untuk membangun URL, biasanya dibangun dengan subfolder. Misalnya, kita memiliki website  blog dengan beberapa kategori di dalamnya dengan folder kategori di dalam sufolder tersebut. Contohnya bisa kurang lebih seperti ini folder yang akan di bangun



## Perlindungan dari CSRF


```html
<form action="<?=base_url('login/authenticate');?>" method="post">
<input type="hidden" name="csrf-token" value="{{$csrfToken}}">
</form>
```

## Redirect Routes