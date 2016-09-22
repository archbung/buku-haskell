# List Comprehension

Selain dengan menuliskan satu per satu anggotanya atau menggunakan range, list
dapat juga dibuat dengan menggunakan list comprehension.  List comprehension
dapat dipandang sebagai range *on steroid*, dimana kita dapat menggunakan
aturan-aturan yang lebih kompleks. 

Sebagai contoh, kita tentu masih ingat dengan teorema Pythagoras.  Kita juga
mengenal istilah tripel Pythagoras, yaitu tiga bilangan bulat positif yang
memenuhi teorema tersebut.  Berikut ini adalah list comprehension yang dapat
digunakan untuk menghasilkan tripel Pythagoras yang lebih kecil dari $$1000$$.
```haskell
tri = [(c,b,a) | a <- [1..999], b <- [1..a], c <- [1..b], a^2 == b^2 + c^2]
```

Perhatikan bahwa suatu list comprehension terdiri dari tiga bagian.
- Keluaran yang berada di sebelah kiri dari `|`.
- Generator.  Pada contoh di atas, digunakan tiga generator yaitu `[1..999]`,
  `[1..a]`, dan `[1..b]` untuk menghasilkan nilai berturut-turut `a`, `b`, dan
  `c`.  Dengan kata lain, `a` memiliki kemungkinan nilai dari $$1$$ sampai
  $$999$$.
- Sebuah filter (opsional).  Pada contoh di atas, filter yang digunakan adalah
  `a^2 == b^2 + c^2`.


## Lab 9

- Tentukan tipe dari ekspresi `tri` di atas.
- Hilangkan filter dari ekspresi `tri` di atas.  Bagaimana nilai dari `tri`
  sekarang? 
- Gunakan list comprehension untuk menghasilkan list berisi bilangan kubik
  (pangkat tiga). 
- Tentukan nilai dari $$1+0.5+0.25+\ldots$$
- Gunakan list comprehension untuk menghasilkan list yang berisi bilangan
  kelipatan $$3$$ atau $$5$$ tetapi bukan kelipatan dari keduanya.

