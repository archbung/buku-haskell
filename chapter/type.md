# Sekilas Mengenai Tipe

Secara sederhana, tipe memberi tahu kita mengenai data apa yang terkandung di dalam suatu variabel.
Sebagai contoh, `5` bisa jadi memiliki tipe `Int` sehingga kita tahu bahwa `5` adalah bilangan bulat.

Haskell adalah bahasa dengan *static typing*, artinya tipe dari setiap ekspresi dapat diketahui pada *compile-time*.
Kombinasi antar ekspresi yang tipe-nya tidak cocok adalah ekspresi yang tidak valid dan akan menghasilkan error kompilasi.
Sebagai contoh, ekspresi `"pradityo" * "utomo"` adalah ekspresi yang tidak valid karena seharusnya kedua argumen fungsi `(*)` adalah bilangan.

Haskell memiliki sistem tipe yang lebih canggih dibandingkan dengan bahasa pemrograman lain.
Pada Haskell, setiap ekspresi memiliki tipe tertentu.
Ini berarti tidak hanya variabel yang memiliki tipe; fungsi pun memiliki tipe tersendiri.
Namun demikian, kita tidak perlu menuliskan tipe dari suatu ekspresi/fungsi seperti bahasa C misalnya.
Karena sistem tipe Haskell, GHC dapat mengetahui tipe dari ekspresi/fungsi secara otomatis.
Selain itu, adanya [sistem tipe] dapat membantu kita untuk menuliskan program secara lebih elegan.

[sistem tipe]: (chapter/type-system.md)

Kita dapat melihat tipe dari setiap ekspresi Haskell dengan menggunakan GHCI. Untuk itu, terdapat dua cara:

- Menggunakan perintah `:set +t` pada GHCI. Masukkan perintah ini pada prompt GHCI, maka setiap ekspresi yang dievaluasi berikutnya akan ditampilkan nilai dan juga tipenya.
- Mengevaluasi suatu ekspresi, lalu menjalankan perintah `:t it`, dimana `it` menunjuk kepada ekspresi terakhir yang dievaluasi.


## Lab 6

Periksa tipe dari setiap ekspresi pada **Lab 2** dan setiap fungsi pada **Lab 5** menggunakan GHCI.
