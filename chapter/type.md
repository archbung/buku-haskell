# Sekilas Mengenai Tipe

Secara sederhana, tipe memberi tahu kita mengenai data apa yang terkandung
di dalam suatu variabel.  Sebagai contoh, `5` bisa jadi memiliki tipe
`Int` sehingga kita tahu bahwa `5` adalah bilangan bulat.

Haskell adalah bahasa dengan *static typing*, artinya tipe dari setiap
ekspresi dapat diketahui pada *compile-time*.  Kombinasi antar ekspresi
yang tipe-nya tidak cocok adalah ekspresi yang tidak valid dan akan
menghasilkan error.  Sebagai contoh, ekspresi 
```
"pradityo" + "utomo"
``` 
adalah ekspresi yang tidak valid karena seharusnya kedua
argumen fungsi `(+)` adalah bilangan.

Pada Haskell, setiap ekspresi memiliki tipe tertentu.  Hal ini berarti
tidak hanya variabel yang memiliki tipe, fungsi pun memiliki tipe
tersendiri.  Berbeda dengan bahasa pemrograman seperti C, GHC dapat
melakukan inferensi tipe dari ekspresi yang valid sehingga pemrogram tidak
harus menuliskannya sendiri.

Kita dapat melihat tipe dari setiap ekspresi Haskell dengan menggunakan
GHCI. Untuk itu, terdapat dua cara:

- Menggunakan perintah `:set +t` pada GHCI.  Masukkan perintah ini pada
  prompt GHCI, maka setiap ekspresi yang dievaluasi berikutnya akan
  ditampilkan nilai dan juga tipenya.
- Mengevaluasi suatu ekspresi, lalu menjalankan perintah `:t it`, dimana
  `it` menunjuk kepada ekspresi terakhir yang dievaluasi.
- Atau dengan perintah `:t [ekspresi]`.  Dengan cara ini kita dapat
  melihat tipe dari suatu ekspresi tanpa perlu mengevaluasinya.

Sebagai contoh, untuk melihat tipe dari fungsi `div`:
```
Prelude> :t div
div :: Integral a => a -> a -> a
```
Tampak bahwa fungsi `div` mengambil dua argumen bertipe `a` dan
menghasilkan satu keluaran bertipe `a`, dimana `a` memiliki kelas tipe
`Integral`.  Lebih lanjut mengenai apa saja tipe dan kelas tipe Haskell
akan dibahas pada bab berikutnya.  Pada saat ini, yang perlu kita ketahui
adalah bahwa setiap ekspresi Haskell memiliki tipe dan kita dapat
mengetahui tipenya dengan bantuan GHCI.

Selain memiliki *static typing*, Haskell juga *strict* dalam hal
kesesuaian tipe.  Ketidak-sesuaian tipe akan selalu menyebabkan error.
Karena itu, mengetahui tipe dari sebuah ekspresi Haskell adalah hal yang
sangat penting.

Kita dapat pula mendeklarasikan tipe dari suatu variabel dengan
menggunakan `::`.  Tentu saja, apabila deklarasi tipe yang kita berikan
tidak benar, akan terjadi error.
```
Prelude> 10 :: Int
10
Prelude> :t it
it :: Int
Prelude> "pradityo" :: Int

<interactive>:1:1: error:
    • Couldn't match expected type ‘Int’ with actual type ‘[Char]’
    • In the expression: "pradityo" :: Int
      In an equation for ‘it’: it = "pradityo" :: Int
```


## Lab 6

Periksa tipe dari setiap ekspresi pada **Lab 2** dan setiap fungsi pada
**Lab 5** menggunakan GHCI.
