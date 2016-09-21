# Sekilas Mengenai Fungsi

Haskell adalah bahasa pemrograman fungsional sehingga fungsi di dalam Haskell adalah *first-class citizen*, seperti halnya variabel adalah *first-class citizen* pada bahasa pemrograman imperatif seperti C.
Ini berarti fungsi dalam Haskell dapat menjadi masukan maupun keluaran bagi fungsi yang lain.

Fungsi di dalam Haskell adalah fungsi yang *pure*, yang berarti fungsi-fungsi tersebut tidak dapat menghasilkan efek samping seperti menuliskan sesuatu ke layar maupun mengubah variabel global seperti pada bahasa pemrograman lain.
Karena itu, fungsi-fungsi dalam Haskell akan selalu menghasilkan nilai yang sama apabila diberikan argumen yang sama.
Sifat ini disebut sebagai *referential transparency*.
Karena sifat *referential transparency* dan [*immutable variable*] inilah Haskell disebut sebagai *pure functional programming language*.

Pada **Lab 2**, pembaca telah bertemu dengan beberapa fungsi standar Haskell, seperti `reverse`, `head`, dan `tail`.
Pembaca juga telah mencoba melihat apa fungsi dari fungsi-fungsi tersebut dengan mengaplikasikannya, misalnya dengan mengevaluasi ekspresi `reverse [1,2,3,4]`.
Nilai dari ekspresi ini ditampilkan ke layar oleh GHCI; `reverse` tidak dapat menampilkan apapun ke layar.

[*immutable variable*]: (chapter/immutable.md)


## Aplikasi Fungsi

Sebagian pembaca yang jeli dapat mengamati perbedaan cara pengaplikasian fungsi pada Haskell dan pada bahasa pemrograman lain.
Pada Haskell, fungsi dan argumennya dipisahkan dengan *spasi*:
```
head "pradityo"
head $ "pradityo"
```
berbeda dengan bahasa C misalnya, dimana fungsi antara fungsi dan argumennya dipisahkan dengan tanda kurung:
```c
tukar (10, 20);
```


## Operator

Setiap operator Haskell pada dasarnya adalah fungsi yang mengambil dua argumen. Sebagai contoh, operator `-` adalah fungsi `(-)` sehingga ekspresi `5 - 3` sama dengan `(-) 5 3`. Sebaliknya, kita dapat pula mengubah fungsi dengan dua argumen menjadi operator, misalnya `div 5 3` ekuivalen dengan ``5 `div` 3``.

Operator Haskell memiliki daya ikat (*precedence*) yang berbeda-beda, misalnya `*` mengikat lebih kuat daripada `+` sehingga dievaluasi terlebih dahulu.
Operator Haskell dengan daya ikat paling kuat adalah "operator" aplikasi fungsi yaitu spasi.
Seperti biasa, kita dapat mengubah urutan evaluasi ekspresi dengan menggunakan tanda kurung seperti biasa. Ekspresi `(5 + 3) / 2` akan menghasilkan `4.0`, bukan `6.5`.


## Fungsi Pertama

Let's make our first Haskell function!

Untuk mendefinisikan fungsi dalam Haskell, gunakan dua aturan berikut:

- Nama fungsi diawali huruf kecil
- Deklarasi fungsi dimulai dengan menuliskan nama fungsinya, lalu diikuti dengan nama argumennya dengan dipisahkan oleh spasi dan diakhiri dengan `=`, lalu masukkan definisi fungsinya.

```
double x = 2 * x
```

## Lab 5

Buatlah fungsi untuk menghitung ekspresi-ekspresi berikut, lalu simpan ke dalam file `fungsi.hs`.

- $$(x - y) * (x + y)$$
- $$(x - y) * (x - y)$$
- Jumlah dari $$n$$ suku pertama barisan $${1,2,3..}$$
- Jumlah dari $$n$$ suku pertama barisan $${1,4,9..}$$

Muat file `fungsi.hs` ke dalam GHCI lalu periksa apakah fungsi yang dibuat sudah benar.
