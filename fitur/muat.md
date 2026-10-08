# Muat

Untuk memuat berkas menggunakan kata kunci `muat` di awal berkas, lalu lokasi-lokasi berkas yang akan di muat dengan tanda kutip dua `"`.

Rumus:
```
muat (alias? "nama_berkas.ns")+
```

Contoh:
```
muat std "std.ns" "inti.ns"
```

```
muat
std "std.ns" 
"inti.ns"
```

---

Gunakan alias jika ingin mengakses fungsi, variabel, dll yang bersifat publik/eksternal di suatu berkas.

```
muat
std "std.ns" 
"inti.ns"

std.cetak("Halo Dunia!")
```

---