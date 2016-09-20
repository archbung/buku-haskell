# GHC

GHC \(Glasgow Haskell Compiler\) adalah compiler Haskell yang paling banyak digunakan. Selain itu, juga terdapat REPL \(Read-Eval-Print-Loop\) atau intepreter Haskell yaitu GHCI \(GHC Interpreter\).

Apabila perintah `stack setup` yang kita jalankan pada Lab 1 berjalan dengan baik, di komputer kita telah terpasang GHC dan GHCI. Untuk membuka GHCI, jalankan perintah berikut.

```
$ stack ghci
```

Apabila tidak ada error, akan muncul tampilan sebagai berikut.

```
GHCi, version 8.0.1: http://www.haskell.org/ghc/  :? for help
Loaded GHCi configuration from /tmp/ghci12235/ghci-script
Prelude>
```

Kita dapat memasukkan ekspresi Haskell pada prompt GHCI. Secara sederhana, ekspresi adalah potongan kode yang dapat menghasilkan suatu nilai tertentu. Kalau kita mengingat bahwa suatu program adalah aturan bagi komputer dalam melakukan suatu komputasi, maka proses komputasi dalam Haskell pada dasarnya adalah evaluasi dari berbagai ekspresi yang ada di dalam suatu program Haskell.

Tekan enter untuk mengevaluasi ekspresi tersebut dan melihat nilainya.

```
Prelude> 5 + 7
12
Prelude> "unmer madiun"
"unmer madiun"
```

Selain dapat mengevaluasi ekspresi yang diberikan secara langsung melalui prompt, GHCI juga dapat mengevaluasi ekspresi-ekspresi yang ada di dalam sebuah file. Misalkan kita ingin memuat file `lab_1.hs` yang berisi ekspresi-ekspresi Haskell, kita dapat melakukannya dengan menggunakan perintah `:l` ("load") sebagai berikut.

```
Prelude> :l lab_1.hs
[1 of 1] Compiling Main             ( lab_1.hs, interpreted )
Ok, modules loaded: Main.
*Main>
```

Perhatikan bahwa prompt GHCI berubah menjadi `*Main>`.

Apabila kita melakukan perubahan pada file `lab_1.hs` dan ingin agar perubahan tersebut dimuat ke dalam GHCI, kita dapat menggunakan perintah `:r` ("reload") sebagai berikut.

```
*Main> :r
[1 of 1] Compiling Main             ( lab_1.hs, interpreted )
Ok, modules loaded: Main.
*Main>
```

## Lab 2

Perhatikan ekspresi-ekspresi berikut dan perkirakan nilainya, lalu masukkan ke dalam GHCI dan perhatikan nilainya.
```
5 + 5.0
5 / 3 + 2
div 5 3 + 2
5 / (3 + 2)
5 * 5
5 ^ 5
5 ** 5
5 - 3
5 * -3
5 * (-3)
"pradityo"
"pradityo" == "utomo"
[1,2,3,4]
[1..4]
1 : [2,3,4]
'p' : "radityo"
"pradityo" ++ " utomo"
head [1,2,3,4]
tail [1,2,3,4]
reverse [1,2,3,4]
head (reverse [1,2,3,4])
(27, "pradityo utomo")
fst (27, "pradityo utomo")
snd (27, "pradityo utomo")
```

## Lab 3

Tuliskan ekspresi-ekspresi berikut ke dalam sebuah file yang diberi nama `pertama.hs`, lalu masukkan ke dalam GHCI

```
a = 10 + 5
b = a + 1
c = a * a
nama_depan = "pradityo"
nama_belakang = "utomo"
motto = "you will never walk alone"
nama_aneh_1 = reverse nama_depan ++ reverse nama_belakang
nama_aneh_2 = reverse (nama_depan ++ nama_belakang)
```

Perkirakan nilai dari masing-masing ekspresi, lalu evaluasi masing-masing ekspresi tersebut dengan menuliskan namanya pada prompt GHCI seperti berikut.

```
Prelude> a
15
```

## Lab 4

Tambahkan `nama_depan = "hizbullah"` di akhir `pertama.hs`, lalu muat kembali ke dalam GHCI dengan perintah `:r`. Perhatikan apa yang terjadi.

Hapus baris `nama_depan = "hizbullah"` dari `lab_3.hs` dan tambahkan baris `d = d + 1`. Muat kembali file ini, lalu evaluasi nilai `d. `

>Untuk menghentikan proses evaluasi, tekan **Ctrl-C**.

