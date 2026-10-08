# Cara Kerja Muat Berkas

Berkas hanya dapat dimuat sekali.
```
# utama.ns
muat 
"std.ns" # di muat
"std.ns" # di hiraukan
```

---

Lokasi berkas relatif terhadap direktori berkas utama dan direktori kode pada direktori instalasi Nusa.

```
# Direktori proyek
e/f/g.ns
c/d.ns
b.ns
a.ns
```

```
# e/f/g.ns
muat
"b.ns"
"c/d.ns"

---

# c/d.ns
muat
"e/f/g.ns"

---

# b.ns
muat
"c/d.ns"

---

# a.ns
muat
"b.ns"
"c/d.ns"
```

Disini tidak akan terjadi circular dependency hell / neraka ketergantungan melingkar karena berkas hanya bisa di muat sekali, dan semua berkas akan di muat dalam saat proses peleksiman.

```
# Urutan berkas yang di muat
e/f/g.ns
c/d.ns
b.ns
a.ns
```

Karena berhubung lokasi berkas juga relatif terhadap direktori kode pada instalasi Nusa, ini dapat menimbulkan ambiguitas, karena jika di direktori berkas utama dan instalasi Nusa terdapat berkas yang sama, contoh:

```
# Direktori instalasi nusa
kode/std/keluar.ns
kode/std/cetak.ns
kode/std.ns -> muat std/keluar.ns, std/cetak.ns
nusa

# Direktori proyek
kode/std/cetak.ns
kode/utama.ns -> muat std.ns, std/cetak.ns
```

ini `std/cetak.ns` mana yang akan di muat? yang ada di direktori instalasi utama atau direktori proyek?

Dari pada mengakali dan membuat nya menjadi rumit, kamu harus memperlakukan kode standar nusa sebagai bagian dari proyek kamu, kecuali kamu tidak membutuhkan nya.

Jika terdeteksi Nusa akan memberikan info dan tidak melajutkan proses, untuk membuat nya tetap jelas dan terprediksi.

---