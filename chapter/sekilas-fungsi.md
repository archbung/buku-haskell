# Sekilas Mengenai Fungsi

Haskell memperlakukan fungsi sebagai *first-class citizen*.  Dalam Haskell, tidak hanya variabel yang dapat menjadi masukan maupun keluaran dari sebuah fungsi, fungsi pun demikian.  Kita dapat membuat suatu fungsi `foo` yang menghasilkan sebuah fungsi `bar` dan mengambil fungsi `quux` sebagai masukan.

Selain merupakan *first-class citizen*, fungsi Haskell adalah fungsi yang
*pure*.  Fungsi Haskell tidak dapat menghasilkan efek samping seperti
menuliskan sesuatu ke layar maupun mengubah variabel global seperti pada
bahasa pemrograman lain.

Karena sifat *pure* ini, fungsi Haskell akan selalu menghasilkan nilai
yang sama apabila diberikan argumen yang sama.  Sifat ini disebut sebagai
*referential transparency*.

Pada **Lab 2**, kita telah bertemu dengan beberapa fungsi standar Haskell,
seperti `reverse`, `head`, dan `tail`.  Kita juga telah mencoba melihat
apa fungsi dari fungsi-fungsi tersebut dengan mengaplikasikannya, misalnya
dengan mengevaluasi ekspresi `reverse [1,2,3,4]`.  Perlu diperhatikan
bahwa yang menampilkan hasilnya ke layar adalah GHCI; `reverse` tidak
dapat menampilkan apapun ke layar.


## Aplikasi Fungsi

Pada Haskell, fungsi dan argumennya dipisahkan dengan spasi.  Sebagai
contoh, ekspresi berikut mengaplikasikan fungsi `head` kepada string
`"pradityo"`.  Nama fungsinya adalah `head`, sedangkan argumennya adalah
`"pradityo"`.
```
head "pradityo"
```
Hal in berbeda dengan bahasa C misalnya, dimana antara fungsi dan
argumennya dipisahkan dengan tanda kurung:
```c
tukar (10, 20);
```


## Operator

Setiap operator Haskell pada dasarnya adalah fungsi yang mengambil dua
argumen.  Sebagai contoh, operator `-` adalah fungsi `(-)` sehingga
ekspresi `5 - 3` sama dengan `(-) 5 3`.  Sebaliknya, kita dapat pula
mengubah fungsi dua argumen menjadi operator, misalnya ekspresi `div 5 3`
ekuivalen dengan ``5 `div` 3``.

Operator Haskell memiliki daya ikat atau *precedence* yang berbeda-beda.
Konsep *precedence* init sudah kita kenal sejak sekolah dasar.  Misalnya
`*` mengikat lebih kuat daripada `+` sehingga dievaluasi terlebih dahulu.
Seperti biasa, kita dapat mengubah urutan evaluasi ekspresi dengan
menggunakan tanda kurung seperti biasa. Ekspresi `(5 + 3) / 2` akan
menghasilkan `4.0`, bukan `6.5`.


## Fungsi Pertama

Untuk mendefinisikan fungsi dalam Haskell, gunakan dua aturan berikut:

- Nama fungsi diawali huruf kecil
- Deklarasi fungsi dimulai dengan menuliskan nama fungsinya, lalu diikuti dengan nama argumennya dengan dipisahkan oleh spasi dan diakhiri dengan `=`.
- Masukkan definisi fungsinya setelah tanda `=`.

```haskell
double x = 2 * x
```

## Lab 5

Buatlah fungsi untuk menghitung ekspresi-ekspresi berikut, lalu simpan ke
dalam file `fungsi.hs`.

- $$(x - y) * (x + y)$$
- $$(x - y) * (x - y)$$
- Jumlah dari $$n$$ suku pertama barisan $${1,2,3..}$$
- Jumlah dari $$n$$ suku pertama barisan $${1,4,9..}$$

Muat file `fungsi.hs` ke dalam GHCI lalu periksa apakah fungsi yang dibuat
sudah benar.
