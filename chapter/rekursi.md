# Rekursi

Seperti telah disinggung sebelumnya, Haskell tidak mengenal konstruksi
perulangan atau *looping* tradisional seperti `for` dan `while` karena
kedua kosntruksi tersebut mensyaratkan variabel yang dapat berubah
nilainya.  Untuk menangani perulangan, Haskell menggunakan rekursi.

Ketika kita mendefinisikan sesuatu secara rekursif, kita mendefinisikan hal tersebut menggunakan dirinya sendiri.  Apabila kita melihat definisi dari fungsi `faktorial` pada sebelumnya, kita akan melihat bahwa `faktorial` didefinisikan secara rekursif.
```haskell
faktorial 0 = 1
faktorial n = n * faktorial (n - 1)
```
Tampak bahwa faktorial dari $$n$$ didefinisikan dalam faktorial bilangan yang lain, yaitu $$n-1$$. 

Secara umum, untuk mendefinisikan fungsi secara rekursif, kita harus
menentukan dua hal:
- Kasus dasar, yaitu kasus yang mudah, yang definisinya langsung dapat
  ditentukan.  Pada `faktorial` di atas, kasus dasarnya adalah `faktorial
  0`. 
- Kasus rekursif.  Dalam menangani kasus rekursif, kita harus memastikan
  agar kasus rekursif ini dapat direduksi menjadi kasus dasar.  Hal ini
  penting agar evaluasi dapat berhenti dan mengeluarkan hasil yang
  diharapkan.  Pada definisi rekursif `faktorial` di atas, berapapun nilai $$n$$ akan tereduksi menjadi $$0$$ (sehingga menjadi kasus dasar) karena adanya $$(n - 1)$$.

Secara teoritis, kita dapat menggunakan rekursi untuk mendefinisikan
fungsi apapun menggunakan Haskell, sehingga penting bagi kita untuk
terbiasa dengan cara penyelesaian problem secara rekursif.
