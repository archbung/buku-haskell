# Immutable Variable

Di **Lab 3**, sebagian pembaca (terutama yang familiar dengan bahasa pemrograman lain) mungkin menemui beberapa kejutan.

Pertama, ketika terdapat dua variabel `nama_depan` di dalam file `pertama.hs` yang masing-masing berisi `"pradityo"` dan `"hizbullah"`, maka GHCI mengeluarkan pesan error sebagai berikut.

```
Prelude> :l pertama.hs
[1 of 1] Compiling Main         ( lab_1.hs, interpreted )

pertama.hs:3:1: error:
    Multiple declarations of ‘nama_depan’
    Declared at: pertama.hs:1:1
                 pertama.hs:3:1
Failed, modules loaded: none.
```

Yang kedua adalah ketika ekspresi `d = d + 1` ternyata melakukan *increment* pada variabel `d`. Yang terjadi adalah evaluasi `d` tidak akan selesai sehingga harus dihentikan dengan menekan **CTRL-C**.

Berbeda dengan bahasa pemrograman lainnya, variabel Haskell bukan merupakan suatu wadah yang isinya dapat berubah-ubah. Variabel Haskell adalah nama dari suatu ekspresi. Dengan kata lain, ekspresi `a = b + c` bukanlah sebuah *assignment* melainkan sebuah definisi; ekspresi tersebut tidak dibaca sebagai  **a berisi nilai b ditambah dengan nilai c** melainkan **a adalah b ditambah c**.

Inilah mengapa evaluasi ekspresi `d = d + 1` tidak akan selesai. Proses evaluasi ini dapat diilustrasikan sebagai berikut.
```
d = d + 1
    { definisi d }
d = (d + 1) + 1
    { definisi d }
d = ((d + 1) + 1) + 1
...
```
