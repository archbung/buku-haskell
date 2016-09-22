# Immutable Variable

Di **Lab 3**, sebagian dari kita yang familiar dengan bahasa pemrograman
lain mungkin menemui beberapa kejutan.

Pertama, ketika terdapat dua variabel `nama_depan` di dalam file
`pertama.hs` yang masing-masing berisi `"pradityo"` dan `"hizbullah"`,
maka GHCI mengeluarkan pesan error sebagai berikut.
```
Prelude> :l pertama.hs
[1 of 1] Compiling Main         ( lab_1.hs, interpreted )

pertama.hs:3:1: error:
    Multiple declarations of ‘nama_depan’
    Declared at: pertama.hs:1:1
                 pertama.hs:3:1
Failed, modules loaded: none.
```

Yang kedua adalah ekspresi `d = d + 1` ternyata tidak melakukan
*increment* pada variabel `d`.  Yang terjadi adalah evaluasi `d` tidak
akan selesai sehingga harus dihentikan dengan menekan \<CTRL-C>.

Kedua hal di atas terjadi karena variabel dalam Haskell adalah nama dari
suatu ekspresi, bukan sebuah wadah yang isinya dapat berubah-ubah.
Ekspresi `a = b + c` bukanlah sebuah *assignment* melainkan sebuah
definisi.

Inilah mengapa evaluasi ekspresi `d = d + 1` tidak akan selesai. Proses evaluasi ini dapat diilustrasikan sebagai berikut.
```
d = d + 1
    { definisi d }
d = (d + 1) + 1
    { definisi d }
d = ((d + 1) + 1) + 1
...
```

Variabel yang tidak dapat berubah nilainya atau *immutable variable* ini
mengharuskan kita untuk mengubah cara kita dalam melakukan pemrograman.
Sebagai contoh, *immutable variable* membuat kita tidak mungkin melakukan
perulangan dengan menggunakan `for` dan sejenisnya, karena konstruksi
demikian mensyaratkan adanya variabel yang nilainya dapat berubah.
