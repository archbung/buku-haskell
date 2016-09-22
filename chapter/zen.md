# Zen of Programming

Tujuan dari pembuatan sebuah program adalah untuk menyelesaikan sebuah
permasalahan.  Tujuan dari bahasa pemrograman adalah membantu pemrogram
dalam membuat program.

Di sini penulis ingin berargumen bahwa ada dua kriteria yang penting
dimiliki oleh bahasa pemrogaman untuk menghasilkan program yang baik.
Program yang baik tentu saja adalah program yang benar, handal, dan dapat
dieksekusi dengan cepat.  Kedua kriteria tersebut adalah:

- *Composability*.  Pembuatan program pada dasarnya mirip dengan bermain
  Lego.  Pemrogram diberikan bagian-bagian kecil berupa konstruksi,
  sintaks, dan fungsi-fungsi, lalu menyusun bagian-bagian tersebut menjadi
  bagian yang lebih besar.  Semakin mudah hal tersebut dilakukan, maka
  *composability* semakin baik.
- *Reusability*.  Permasalahan-permasalahan yang hampir sama tentu
  memerlukan solusi yang mirip.  Penjumlahan isi suatu larik atau list
  tentu memiliki bagian lojik yang sama tidak peduli apakah larik tersebut
  berisi bilangan bulat atau bilangan real.  Semakin mudah bagi pemrogram untuk menghasilkan solusi yang umum, maka *reusability* semakin baik.

Dalam hal ini, Haskell adalah bahasa pemrograman dengan skor *composability* dan *reusability* yang sangat baik.


## Composability

Sekilas tampak bahwa *immutable variable*, *pure function*, dan sistem tipe yang *static* dan *strict* adalah sifat-sifat yang merepotkan.  Ambil contoh *pure function*.  Kalau suatu program tidak dapat menghasilkan *side-effect*, apa kegunaan dari program tersebut?  Bagaimanapun juga, hal-hal berguna yang dapat dilakukan oleh sebuah program hampir semuanya merupakan *side-effect*, seperti membaca masukan pengguna, memanipulasi suatu file, atau menampilkan hasil komputasi ke layar.

Sifat *pure* dari Haskell ini merupakan sebuah *trade-off*. Sebuah fungsi
yang mampu menghasilkan *side-effect* selalu memiliki efek (misalnya
mengubah variabel global) atau mengambil argumen yang tidak eksplisit. Hal
ini menyebabkan komposisi (dalam arti yang umum) antar fungsi yang
memiliki *side-effect* menjadi sulit, karena komposisi fungsi harus
memperhitungkan efek maupun argumen yang tidak eksplisit tersebut.  Selain
itu, karena bisa jadi keluaran fungsi tersebut bergantung kepada argumen
yang tidak eksplisit, maka apabila fungsi tersebut dipanggil dua kali
dengan argumen eksplisit yang sama hasilnya bisa jadi berbeda.  Karena
setiap program yang dibuat pasti mengandung bug dan belum tentu benar,
dengan adanya *side-effect* proses debugging dan analisis program menjadi
lebih sulit.  Dalam hal ini, Haskell memilih kemudahan proses debugging
dan analisis program di atas kenyamanan.

Well, akan tetapi *side-effect* tetaplah sesuatu yang diperlukan.  Sebagai
solusinya, Haskell memisahkan antara bagian kode yang dapat menghasilkan
*side-effect* dengan bagian kode yang *pure*.  Untuk mengelola
*side-effect* (termasuk mengelola komposisi dari fungsi-fungsi yang
menghasilkan *side-effect*), Haskell menggunakan suatu konstruksi yang
disebut sebagai Monad.  Monad ini sayangnya merupakan sebuah topik lanjut
dalam Haskell, sehingga di luar scope dari buku ini.  Bagi pembaca yang
tertarik untuk mendalami Monad, saat ini sudah banyak tutorial mengenai
Monad yang tersedia di Internet.

*Static* dan *strict typing* juga sangat membantu dalam melakukan
komposisi fungsi.  Apabila tipe dari ekspresi bersifat dinamis (baru dapat
ditentukan pada saat *runtime*) dan tidak *strict*, maka sulit bagi
*compiler* untuk memastikan apakah suatu komposisi fungsi adalah ekspresi
yang valid.  Lagi-lagi ini adalah sebuah *trade off* antara kenyamanan dan
*correctness* dan Haskell memilih *correctness*.


## Reusability

Dengan adanya kelas tipe, Haskell dapat menghasilkan fungsi-fungsi yang
umum (*general*) dengan tetap mempertahankan *correctness* dari fungsi
tersebut.  Sebagai contoh, terdapat sebuah fungsi standar untuk
menjumlahkan isi dari suatu list yaitu `sum` yang juga telah kita jumpai
di **Lab 2**.  Tipe dari `sum` adalah:
```
Prelude> :t sum
sum :: (Foldable t, Num a) => t a -> a
```

Perhatikan bahwa tipe keluaran dari fungsi sum memiliki kelas `Num`. Hal
ini berarti nilai dari `sum` adalah bilangan apa saja, baik itu `Int`,
`Float`, dan sebagainya.  Dengan kata lain, kita tidak perlu membuat
fungsi sejenis yang terpisah untuk menangani tipe keluaran yang
berbeda-beda, asalkan tipe keluaran tersebut adalah bilangan.

Lebih dari itu, tipe masukan dari `sum` adalah `t a` dimana `t` adalah
`Foldable` (yang kurang lebih bermakna sesuatu yang dapat "digulung",
misalnya list) dan keluarannya adalah suatu bilangan `a`.  Jadi apabila
fungsi `sum` diberi masukan berupa list yang berisi `Int`, keluarannya
akan bertipe `Int`.  Apabila diberi masukan berupa list yang berisi
`Float`, keluarannya akan bertipe `Float`.  Dapat kita lihat bahwa kelas
tipe Haskell memungkinkan pembuatan program yang cukup *general* tetapi
tetap benar.

>Llebih lanjut mengenai `Foldable` akan dibahas pada bab mengenai fungsi orde tinggi.
