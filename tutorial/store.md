📚 Dokumentasi Command Store

Dokumentasi lengkap untuk semua command yang tersedia di modul Store bot WhatsApp.
Semua command di bawah ini tidak memerlukan prefix (kecuali disebutkan), jadi kamu bisa langsung mengetikkan command-nya.

---

📋 Daftar Isi

1. Pendahuluan
2. Command untuk Customer
   · .list – Lihat semua kategori produk
   · .product / .cek – Lihat detail produk dalam kategori
   · .buy – Beli produk
   · .cart – Keranjang belanja
   · .addcart – Tambah ke keranjang
   · .delcart – Hapus dari keranjang
   · .clearcart – Kosongkan keranjang
   · .checkout – Checkout keranjang
   · .confirm – Konfirmasi pembayaran
   · .cancel – Batalkan order
   · .myorder – Lihat riwayat pesanan
   · .review – Beri rating & review
   · .wl / .wishlist – Wishlist favorit
   · .addwl – Tambah ke wishlist
   · .delwl – Hapus dari wishlist
   · .clearwl – Kosongkan wishlist
   · .notifyme – Notifikasi stok habis
   · .coupon – Lihat daftar kupon (customer)
3. Command untuk Owner
   · .addcat – Tambah kategori
   · .editcat – Edit kategori
   · .delcat – Hapus kategori
   · .additem – Tambah produk
   · .edititem – Edit produk
   · .delitem – Hapus produk
   · .setstock – Ubah stok
   · .listcat – Lihat semua kategori (owner)
   · .listitem – Lihat semua item dalam kategori (owner)
   · .orders – Lihat daftar pesanan pending
   · .done – Selesaikan order
   · .cekorder – Cek detail order
   · .addcoupon – Tambah kupon diskon
   · .delcoupon – Hapus kupon
   · .listcoupon – Lihat daftar kupon (owner)
   · .rekap – Export rekap toko ke Excel
   · .topcust – Top 10 customer
4. Alur Belanja
5. Tips & Trik

---

📖 Pendahuluan

Modul Store memungkinkan kamu untuk:

· Menjual produk dengan manajemen kategori, item, stok, dan harga.
· Customer bisa melihat produk, menambahkan ke keranjang, checkout, dan melakukan pembayaran.
· Owner bisa mengelola semua data toko, melihat laporan, dan memproses pesanan.

---

🛍️ Command untuk Customer

.list

Alias: katalog, catalog, produk

Deskripsi:
Menampilkan semua kategori produk yang tersedia di toko.

Penggunaan:

```
.list
```

Contoh Output:

```
꒰ list ꒱
🩰 Netflix
🩰 Spotify
🩰 Game Voucher
```

---

.product / .cek

Alias: produk, cek, harga

Deskripsi:
Menampilkan detail produk dalam satu kategori (nama item, harga, stok).

Penggunaan:

```
.product <nama_kategori>
```

atau langsung ketik nama kategori:

```
netflix
```

Contoh:

```
.product netflix
```

---

.buy

Alias: beli, order

Deskripsi:
Membeli satu produk dan membuat invoice sementara. Order akan masuk ke status pending_user.

Penggunaan:

```
.buy <kategori>/<id_item>
```

Contoh:

```
.buy netflix/1
```

Catatan:

· ID item bisa dilihat dari .product atau .listitem.
· Setelah ini, kamu akan menerima invoice dengan tombol Konfirmasi Bayar dan Batalkan.

---

.cart

Deskripsi:
Menampilkan isi keranjang belanja kamu.

Penggunaan:

```
.cart
```

---

.addcart

Deskripsi:
Menambahkan produk ke keranjang belanja (bisa dengan kuantitas).

Penggunaan:

```
.addcart <kategori>/<id> [qty]
```

Contoh:

```
.addcart netflix/1
.addcart netflix/1 2
```

---

.delcart

Deskripsi:
Menghapus item dari keranjang berdasarkan indeks (lihat .cart untuk indeks).

Penggunaan:

```
.delcart <indeks>
```

Contoh:

```
.delcart 2
```

---

.clearcart

Deskripsi:
Mengosongkan seluruh isi keranjang.

Penggunaan:

```
.clearcart
```

---

.checkout

Alias: co

Deskripsi:
Checkout semua item di keranjang. Jika kamu punya kupon, bisa disertakan.

Penggunaan:

```
.checkout [kode_kupon]
```

Contoh:

```
.checkout
.checkout DISKON10
```

---

.confirm

Alias: konfirmasi

Deskripsi:
Mengonfirmasi pembayaran setelah melakukan transfer. Order akan berubah status menjadi pending_owner dan owner akan menerima notifikasi.

Penggunaan:

```
.confirm <orderId>
```

Contoh:

```
.confirm INV-20260623-0001
```

---

.cancel

Alias: batal

Deskripsi:
Membatalkan order yang masih dalam status pending_user atau pending_owner.

Penggunaan:

```
.cancel <orderId> [alasan]
```

Contoh:

```
.cancel INV-20260623-0001
.cancel INV-20260623-0001 Salah pilih produk
```

---

.myorder

Alias: myorders, pesananku, orderku, riwayat

Deskripsi:
Menampilkan riwayat semua pesanan yang pernah kamu buat.

Penggunaan:

```
.myorder
```

---

.review

Alias: rate, rating

Deskripsi:
Memberi rating dan komentar untuk order yang sudah selesai (completed).

Penggunaan:

```
.review <orderId> <rating 1-5> [komentar]
```

Contoh:

```
.review INV-20260623-0001 5 Mantap banget!
```

---

.wl / .wishlist

Deskripsi:
Menampilkan daftar wishlist (produk favorit) kamu.

Penggunaan:

```
.wl
```

---

.addwl

Deskripsi:
Menambahkan produk ke wishlist.

Penggunaan:

```
.addwl <kategori>/<id>
```

Contoh:

```
.addwl netflix/1
```

---

.delwl

Deskripsi:
Menghapus produk dari wishlist berdasarkan indeks (lihat .wl).

Penggunaan:

```
.delwl <indeks>
```

Contoh:

```
.delwl 2
```

---

.clearwl

Deskripsi:
Mengosongkan seluruh wishlist.

Penggunaan:

```
.clearwl
```

---

.notifyme

Alias: restock, stoknotif

Deskripsi:
Mendaftar untuk mendapatkan notifikasi saat stok produk tertentu tersedia kembali (hanya jika stok sedang habis).

Penggunaan:

```
.notifyme <kategori>/<id>
```

Contoh:

```
.notifyme netflix/1
```

---

.coupon (customer)

Deskripsi:
Menampilkan daftar kupon diskon yang tersedia untuk umum.

Penggunaan:

```
.coupon
```

---

👑 Command untuk Owner

Semua command di bawah ini hanya bisa digunakan oleh owner (nomor yang terdaftar di config.owner.number).

.addcat

Deskripsi:
Menambahkan kategori baru ke toko.

Penggunaan:

```
.addcat <id>|<nama>|<emoji>|<deskripsi>
```

Contoh:

```
.addcat netflix|Netflix|🎬|Akun Netflix sharing
```

---

.editcat

Deskripsi:
Mengedit salah satu field dari kategori (name, emoji, description).

Penggunaan:

```
.editcat <id>|<field>|<nilai>
```

Contoh:

```
.editcat netflix|name|Netflix Premium
.editcat netflix|emoji|📺
```

---

.delcat

Deskripsi:
Menghapus kategori beserta semua item di dalamnya.

Penggunaan:

```
.delcat <id>
```

Contoh:

```
.delcat netflix
```

---

.additem

Deskripsi:
Menambahkan produk baru ke dalam sebuah kategori.

Penggunaan:

```
.additem <kategori>|<nama>|<deskripsi>|<harga>|<stok>
```

Contoh:

```
.additem netflix|2u1d shar|2 user 1 hari sharing|1800|10
```

---

.edititem

Deskripsi:
Mengedit field produk (name, desc, price, stock).

Penggunaan:

```
.edititem <kategori> <id> <field> <nilai>
```

Contoh:

```
.edititem netflix 1 price 2500
.edititem netflix 1 stok 15
```

---

.delitem

Deskripsi:
Menghapus produk dari kategori.

Penggunaan:

```
.delitem <kategori> <id>
```

Contoh:

```
.delitem netflix 1
```

---

.setstock

Deskripsi:
Mengubah stok produk dengan mode set, add (tambah), atau sub (kurang).

Penggunaan:

```
.setstock <kategori> <id> <+/-/angka>
```

Contoh:

```
.setstock netflix 1 +5      # tambah 5
.setstock netflix 1 -3      # kurangi 3
.setstock netflix 1 20      # set menjadi 20
```

---

.listcat

Deskripsi:
Menampilkan semua kategori (termasuk yang tidak visible). Berguna untuk owner.

Penggunaan:

```
.listcat
```

---

.listitem

Deskripsi:
Menampilkan semua item dalam satu kategori.

Penggunaan:

```
.listitem <kategori>
```

Contoh:

```
.listitem netflix
```

---

.orders

Alias: listorder

Deskripsi:
Menampilkan daftar pesanan yang masih pending (status pending_user / pending_owner).

Penggunaan:

```
.orders
```

Untuk melihat semua pesanan (termasuk selesai & batal), tambahkan all:

```
.orders all
```

---

.done

Deskripsi:
Menyelesaikan order (status menjadi completed). Owner akan menerima notifikasi dan struk digital akan digenerate.

Penggunaan:

```
.done <orderId> [catatan]
```

Contoh:

```
.done INV-20260623-0001
.done INV-20260623-0001 Sudah dikirim
```

---

.cekorder

Deskripsi:
Menampilkan detail lengkap satu order berdasarkan ID.

Penggunaan:

```
.cekorder <orderId>
```

Contoh:

```
.cekorder INV-20260623-0001
```

---

.addcoupon

Deskripsi:
Menambahkan kupon diskon baru.

Penggunaan:

```
.addcoupon <kode>|<tipe>|<nilai>|<minorder>|<maxdisc>|<maxusage>|<expiry>
```

· tipe: percent atau fixed
· nilai: besaran diskon
· minorder: minimal total belanja untuk bisa pakai kupon
· maxdisc: maksimal diskon (untuk percent)
· maxusage: maksimal pemakaian (0 = tak terbatas)
· expiry: tanggal kadaluarsa (ISO, opsional)

Contoh:

```
.addcoupon DISKON10|percent|10|10000|5000|100|2026-12-31T23:59:59
```

---

.delcoupon

Deskripsi:
Menghapus kupon berdasarkan kode.

Penggunaan:

```
.delcoupon <kode>
```

Contoh:

```
.delcoupon DISKON10
```

---

.listcoupon

Deskripsi:
Menampilkan semua kupon yang tersedia (termasuk yang sudah expired).

Penggunaan:

```
.listcoupon
```

---

.rekap

Alias: export, excel, laporan

Deskripsi:
Menggenerate file Excel berisi rekap lengkap toko (kategori, item, stok, revenue, dll) dan mengirimkannya sebagai dokumen.

Penggunaan:

```
.rekap
```

---

.topcust

Alias: topcustomer, topbuyer, leaderboard, topshopper

Deskripsi:
Menampilkan top 10 customer berdasarkan total belanja (order selesai).

Penggunaan:

```
.topcust
```

---

🔄 Alur Belanja

Berikut alur lengkap dari customer membeli hingga owner menyelesaikan order:

1. Customer melihat produk
      .list → .product netflix
2. Customer membeli
      .buy netflix/1 → menerima invoice dengan tombol Konfirmasi Bayar dan Batalkan
3. Customer transfer & konfirmasi
      Customer transfer ke rekening owner, lalu:
      .confirm INV-20260623-0001
4. Owner mendapat notifikasi
      Owner menerima pesan berisi detail order dengan tombol Selesaikan Order dan Tolak Order
5. Owner menyelesaikan order
      Owner mengecek pembayaran, lalu:
      .done INV-20260623-0001
6. Customer menerima struk digital
      Customer mendapatkan gambar struk dan status order menjadi completed.
7. Customer bisa memberi review
      .review INV-20260623-0001 5 Mantap!

---

💡 Tips & Trik

· Semua command store tanpa prefix (kecuali ditulis dengan titik di dokumentasi untuk kejelasan).
· Jika kamu lupa format, cukup ketik command tanpa argumen untuk melihat bantuan.
· Gunakan .cart untuk mengumpulkan banyak item sebelum checkout.
· Owner bisa memantau pesanan pending lewat .orders dan menyelesaikannya dengan .done.
· Jangan lupa untuk mengisi config.owner.number agar notifikasi owner berfungsi.

---

📌 Dokumentasi ini berlaku untuk versi terbaru dari modul Store bot WhatsApp.
Jika ada pertanyaan atau saran, hubungi owner bot.
