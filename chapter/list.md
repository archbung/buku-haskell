# List

Berbeda dengan tuple, list hanya bisa menyimpan data yang bertipe sama.  List
bisa dikatakan adalah struktur data yang paling penting dalam Haskell.  Kita
telah menemui beberapa list sebelumnya, seperti `[1,2,3,4]`, `"pradityo"`, dan
`['p','r','a','d','i','t','y','o']`. 
>Ingat bahwa `String` adalah list berisi `Char` sehingga dua list yang terakhir adalah ekuivalen. 

Kita juga telah mencoba mengaplikasikan beberapa fungsi standar yang dapat
bekerja pada list seperti `head`, `tail`, `sum`, dan `(++)`, melihat apa yang
dilakukan oleh fungsi-fungsi tersebut, dan melihat pula tipenya.  Library
standar Haskell berisi banyak fungsi yang bekerja pada list.  Sebagian dari
fungsi-fungsi ini akan menjadi bagian dari **Lab 8**.


## Operator Cons

List adalah tipe data yang rekursif, artinya dalam definisinya mengandung definisi list yang lain. Sebuah list Haskell didefinisikan sebagai:
- list kosong (memiliki sintaks dan tipe `[]`), atau
- sebuah elemen yang disambung di depan list yang lain dengan menggunakan
  operator cons yang disimbolkan sebagai `:`.

Karena list bisa jadi adalah struktur data yang paling penting, maka operator cons adalah operator yang paling penting.  Tipe dari operator cons ini adalah,
```
Prelude> :t (:)
(:) :: a -> [a] -> [a]
```
yang dapat dibaca sebagai "operator cons mengambil sebuah elemen bertipe `a` dan sebuah list berisi `a` (sehingga memiliki tipe `[a]`) untuk menghasilkan list berisi `a`.  Perhatikan bahwa ekspresi di sebelah kiri operator cons (argumen pertama) adalah sebuah elemen sedangkan ekspresi di sebelah kanannya (argumen kedua) adalah sebuah list.  Perhatikan pula bahwa `a` bisa bertipe apa saja, tidak hanya tipe primitif.  Dengan kata lain, kita dapat membuat list di dalam list, tuple di dalam list, dan sebagainya.
```
a = ["pradityo", "utomo"]
b = [[1,2,3],[4,5,6],[7,8,9]]
c = [(10,20),(30,40)]
```

Operator cons berasosiasi ke kanan.  Artinya, apabila ada lebih dari satu operator cons dalam sebuah ekspresi, operator cons yang paling kanan akan dievaluasi terlebih dahulu.  Dengan kata lain, ekspresi-ekspresi berikut ekuivalen:
```haskell
[1,2,3,4]
1 : [2,3,4]
1 : 2 : 3 : 4 : []
```


## Range

Kita dapat mendefinisikan sebuah list dengan menuliskan setiap anggotanya.  Selain itu, kita juga dapat mendefinisikan suatu list dengan menggunakan range sebagai berikut.
```haskell
lower_case = ['a'..'z']
upper_case = ['A'..'Z']
one_to_ten = [1..10]
odd_number = [1,3..]
```


## Lab 8

- Tentukan apa fungsi dan tipe dari `head`, `tail`, `init`, `last`,
  `reverse`, `drop`, `take`, `repeat`, `product`, `and`, `or`, dan `concat`.

- Tentukan tipe dari ekspresi `lower_case`, `upper_case`, `one_to_ten`, dan `odd_number` di atas.

- Gunakan range untuk membuat list yang berisi:
    - bilangan genap
    - bilangan genap kurang dari 100
    - bilangan kelipatan 3
    - bilangan kelipatan 5 yang dimulai dari 15
    - bilangan kelipatan 9 yang dimulai dari 27 dan kurang dari 108
    - alfabet sebelum huruf 'j'
