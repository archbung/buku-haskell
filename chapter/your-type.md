# Create Your Type

Seperti halnya bahasa pemrograman lain, Haskell memungkinkan kita untuk membuat tipe data tersendiri.  Untuk itu, kita menggunakan kata kunci `data`.  Sebagai contoh, lampu lalu lintas di sebuah perempatan dapat kita nyatakan sebagai berikut.
```haskell
data Lampu = Merah | Kuning | Hijau
```
Dari definisi di atas, kita dapat mengetahui bahwa sebuah `Lampu` memiliki nilai `Merah`, `Kuning`, **atau** `Hijau`.

Kita juga dapat mendefinisikan tipe data rekursif.  Sebagai contoh, list Haskell dapat didefinisikan sebagai berikut.
```haskell
data List a = Empty | Cons a (List a)
```
Dari definisi di atas, kita dapat melihat bahwa sebuah `List` berisi `a` adalah list kosong `Empty` **atau** sebuah elemen `a` disambung di depan `List` berisi `a` yang lain.


## Lab 11

Didefinisikan sebuah *binary tree* sebagai berikut.
```haskell
data Tree a = Leaf | (Tree a) Node a (Tree a)
```

- Apabila diberikan sebuah *binary tree* berisi `Int`, buatlah sebuah
  fungsi untuk memperoleh nilai maksimum yang terkandung di dalam *binary
  tree* tersebut.
- Buatlah fungsi untuk mengubah sebuah *binary tree* menjadi sebuah list.
