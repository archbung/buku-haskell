# Tipe Primitif

Haskell memiliki beberapa tipe primitif.
Disebut sebagai "primitif" karena tipe-tipe ini adalah tipe standar.
Tipe-tipe primitif Haskell ditampilkan pada tabel berikut.

| Tipe | Deskripsi |
|--|--|
| `Int` | Bilangan bulat yang ukurannya bergantung pada arsitektur komputer |
| `Integer` | Bilangan bulat dengan presisi sembarang, dapat digunakan untuk menyimpan bilangan yang sangat besar |
| `Float` | Bilangan real (pecahan) dengan presisi tunggal |
| `Double` | Bilangan real dengan presisi ganda |
| `Char` | Berisi karakter Unicode, misalnya `'a'` dan `'b'` |
| `Bool` | Menyatakan nilai *benar* atau *salah* |

Perhatikan bahwa nama tipe selalu dimulai dengan huruf kapital.
Ini adalah salah satu aturan sintaks Haskell, dimana nama variabel/fungsi harus dimulai dengan huruf kecil sedangkan nama tipe harus dimulai dengan huruf kapital.

Haskell tidak melakukan perubahan tipe (*type coercion*) secara otomatis.
Sebagai contoh, Haskell secara otomatis tidak akan mengubah `Int` menjadi `Integer`, walaupun `Int` dan `Integer` sama-sama merepresentasikan bilangan bulat.
Dengan kata lain, potongan kode berikut bukan merupakan ekspresi Haskell yang valid.
```haskell
a = 10 :: Int
b = 5 :: Integer
c = a + b
```

## Lab 6

Ubahlah potongan kode berikut agar dapat dimuat ke dalam GHCI dan `c` dapat diketahui nilainya.
```
a = 26 / 5
b = length ['a'..'z']
c = a / b
```
