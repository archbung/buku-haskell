# Tipe Primitif

Haskell memiliki beberapa tipe primitif.  Disebut sebagai "primitif" karena
tipe-tipe ini adalah tipe standar bawaan Haskell.

| Tipe | Deskripsi |
|--|--|
| `Int` | Bilangan bulat yang ukurannya bergantung pada arsitektur komputer |
| `Integer` | Bilangan bulat dengan presisi sembarang, dapat digunakan untuk menyimpan bilangan yang sangat besar |
| `Float` | Bilangan real (pecahan) dengan presisi tunggal |
| `Double` | Bilangan real dengan presisi ganda |
| `Char` | Berisi karakter Unicode, misalnya `'a'` dan `'b'` |
| `Bool` | Menyatakan nilai *benar* atau *salah* |
| `String` | List berisi `Char` |

Perhatikan bahwa nama tipe selalu dimulai dengan huruf kapital. Ini adalah
salah satu aturan sintaks Haskell, dimana nama variabel/fungsi harus
dimulai dengan huruf kecil sedangkan nama tipe harus dimulai dengan huruf
kapital.

Haskell tidak melakukan perubahan tipe atau *type coercion* secara
otomatis.  Sebagai contoh, Haskell tidak akan mengubah `Int` menjadi
`Integer`, walaupun `Int` dan `Integer` sama-sama merepresentasikan
bilangan bulat.  Akibatnya, potongan kode berikut bukan merupakan ekspresi
Haskell yang valid.

```haskell
a = 10 :: Int
b = 5 :: Integer
c = a + b
```

Agar potongan kode tersebut valid, kita perlu mengubah `a` menjadi bertipe `Integer` atau `b` menjadi bertipe `Int`.  Untuk itu kita dapat menggunakan fungsi `fromIntegral`, misalnya sebagai berikut.

```haskell
a = 10 :: Int
b = 5 :: Integer
c = fromIntegral a + b
```

Hal ini terjadi karena Haskell sangat *strict* terhadap tipe.  Bagi sebagian orang, perubahan tipe yang dilakukan secara otomatis di antara dua tipe yang masuk akal (misalnya antara `Int` dan `Integer`) adalah hal yang lebih disukai.  Di sisi lain, *strict-ness* Haskell terhadap tipe memungkinkan GHC untuk mendeteksi banyak bug pada waktu kompilasi atau *compile-time*, sehingga mengurangi jumlah bug yang akan muncul pada *runtime* secara signifikan.  Secara pribadi, penulis menganggap hal ini adalah *trade-off* yang baik dimana kita mengorbankan sedikit kenyamanan untuk menghasilkan program yang lebih handal.


## Lab 6

- Periksa tipe dari fungsi `fromIntegral`.
- Ubahlah potongan kode berikut agar menjadi ekspresi Haskell yang valid.

```
a = 26 / 5
b = length ['a'..'z']
c = a / b
```
