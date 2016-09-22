# Pattern Matching

Pattern Matching adalah salah satu cara untuk mengambil nilai dari sebuah
ekspresi.  Sebagai contoh, pada ekspresi berikut
```haskell
(a,b) = (10, "juara")
```
`a` akan bernilai `10` sedangkan `b` akan bernilai `"juara"`.  Pada
ekspresi yang lain,
```haskell
(x:xs) = [1,2,3,4]
```
`x` akan bernilai `1` sedangkan `xs` akan bernilai `[2,3,4]`.
> Ingat kembali mengenai operator cons

Pattern matching banyak digunakan dalam mendefinisikan fungsi.  Sebagai contoh, kita dapat mendefinisikan fungsi untuk menentukan $$N$$ faktorial sebagai berikut.
```haskell
faktorial 0 = 1
faktorial n = n * faktorial (n - 1)
```
Fungsi di atas dapat dibaca sebagai berikut.
- Faktorial dari nol adalah satu
- Faktorial bilangan yang lain adalah bilangan tersebut dikali dengan
  faktorial bilangan tersebut dikurangi satu.

Pada contoh fungsi `faktorial` di atas, tampak bahwa pattern matching digunakan seolah-olah sebagai pengganti dari konstruksi kondisional (if, then, else). 

Dalam mendefinisikan fungsi menggunakan pattern matching, kita perlu memperhatikan dua hal:
- Pattern dicocokkan dari atas ke bawah.  Pada contoh fungsi `faktorial`
  di atas, pattern `faktorial 0` harus dituliskan di atas `faktorial n`
  karena `n` bisa sama dengan bilangan berapapun (termasuk $$0$$). Dengan
  menuliskan definisinya demikian, maka kita dapat menangani kasus ketika
  $$n=0$$ dengan baik.
- Fungsi harus menangani semua pattern yang ada dari masukannya.  Pada
  contoh `faktorial` di atas, pattern `n` sudah mencakup semua bilangan
  sehingga definisi `faktorial` di atas sudah terdefinisi untuk semua
  pattern masukannya.  Fungsi yang terdefinisi tidak pada semua pattern
  masukannya disebut sebagai fungsi parsial.


## Lab 10

Buatlah sebuah fungsi untuk 
- menentukan bilangan Fibonacci yang ke 1000
- menentukan panjang dari sebuah list
- membalik sebuah list (tanpa menggunakan `reverse`)
- menyambung dua buah list (tanpa menggunakan `(++)`)
