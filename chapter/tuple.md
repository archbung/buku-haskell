# Tuple

*Tuple* atau pasangan adalah salah satu struktur data primitif yang ada
pada Haskell.  Tuple memungkinkan kita untuk menyimpan data yang tipenya
berbeda.  Sebagai contoh, tuple berikut bisa jadi merepresentasikan entri
data seorang dosen di sebuah Universitas di Jawa Timur,
```haskell
dosen_a = ("utomo", "pradityo", 28, 180, 75, "lektor kepala")
```
dimana
- `"utomo"` adalah nama belakang
- `"pradityo"` adalah nama depan
- `28` adalah usia
- `180` adalah tinggi badan
- `75` adalah berat badan
- `"lektor kepala"` adalah jabatan fungsional.

Kita dapat pula membuat tuple bersarang.  Misalnya dengan membuat tinggi
badan dan berat badan ke dalam tuple tersendiri sebagai berikut.
```haskell
dosen_b = ("utomo", "pradityo", 28, (180, 75), "lektor kepala")
```

Haskell hanya menyediakan fungsi standar untuk tuple dengan dua elemen
yang disebut *pair* atau pasangan.  Kedua fungsi standar itu adalah `fst`
dan `snd`.  Sayangnya, tidak ada cara yang general untuk mengakses elemen
tuple yang ke-$$N$$ sehingga tuple secara umum tidak banyak digunakan.


## Lab 7

- Periksa tipe dari `dosen_a` dan `dosen_b` di atas.
- Periksa tipe dan kegunaan dari `fst` dan `snd`.

