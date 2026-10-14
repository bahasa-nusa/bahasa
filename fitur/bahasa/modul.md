# Modul

Gunakan kata kunci `mod` untuk menggunakan kode dari berkas Nusa lain, diikuti dengan nama modulnya.

```nusa
mod std

std.cetak("Halo Dunia!")
```

## Nama Modul

Nama modul mengikuti nama berkas tanpa ekstensi `.ns`.

Contoh, berkas `std.ns` digunakan sebagai modul `std`.

```nusa
mod std
```

## Deklarasi Modul

Kata kunci `mod` hanya boleh digunakan sekali dan harus berada di bagian paling atas berkas. Kamu bisa memuat beberapa modul dalam satu deklarasi.

```nusa
mod std mtk
```

Atau, tulis setiap nama modul pada baris terpisah.

```nusa
mod
std
mtk
```

Deklarasi `mod` berikut tidak valid karena digunakan lebih dari sekali.

```nusa
mod std
mod mtk # Tidak valid
```

## Modul dalam Direktori

Untuk memuat modul dari dalam direktori, gunakan tanda titik (`.`) sebagai pemisah nama direktori dan berkas.

Contoh, berkas `mtk/op.ns` dimuat dengan cara berikut.

```nusa
mod mtk.op
```

## Urutan Pencarian Modul

Nusa mencari modul dalam urutan berikut:

1. Direktori root proyek.
2. Direktori instalasi Nusa.

Jika nama modul ditemukan di kedua lokasi, Nusa akan menggunakan berkas dari direktori root proyek.

Contoh struktur berkas:

```text
# Direktori instalasi Nusa
std.ns

# Direktori root proyek
std.ns
```

Dengan deklarasi berikut, Nusa akan menggunakan `std.ns` dari direktori root proyek.

```nusa
mod std
```

## Nama Modul yang Sama

Nusa tidak mendukung alias modul. Jika nama modul bertabrakan, gunakan nama berkas atau direktori yang berbeda agar setiap modul bisa dibedakan.

Contoh, jika instalasi Nusa sudah memiliki `std.ns`, kamu bisa menggunakan nama `proyek_std.ns` untuk modul milik proyek.

```text
# Direktori instalasi Nusa
std.ns

# Direktori root proyek
proyek_std.ns
```

Kemudian, muat kedua modul seperti berikut.

```nusa
mod std proyek_std
```

Kamu juga bisa menggunakan nama `std_proyek.ns` di direktori root proyek.

```text
# Direktori instalasi Nusa
std.ns

# Direktori root proyek
std_proyek.ns
```

Lalu, muat modulnya dengan deklarasi berikut.

```nusa
mod std std_proyek
```