# Nusa Language Design

Dokumen ini menetapkan prinsip dan konvensi desain bahasa pemrograman Nusa. Dokumen ini berfokus pada bahasa dan pengalaman pemrograman, bukan tata kelola proyek secara umum.

## 1. Tujuan Desain

Nusa menggunakan bahasa Indonesia sebagai identitas utama sintaksnya. Tujuannya adalah menghadirkan cara menulis program yang jelas dan konsisten bagi penutur Indonesia, tanpa mengorbankan kualitas desain bahasa atau membatasi penggunaan Nusa di tingkat internasional.

Prinsip desain:

- **Indonesia sebagai identitas inti.** Keyword dan elemen inti bahasa mengikuti filosofi bahasa Indonesia.
- **Pengembangan terminologi Indonesia.** Nusa mendorong pengembangan kosakata dan istilah teknis yang berakar dari bahasa Indonesia, termasuk pembentukan istilah baru apabila dapat memperjelas konsep, memperkuat konsistensi terminologi, atau mendukung identitas bahasa. Istilah baru harus didefinisikan dan digunakan secara konsisten.
- **Jelas dan mudah dibaca.** Sintaks sebaiknya mudah dipahami, termasuk oleh pengguna baru.
- **Konsisten.** Fitur baru mengikuti pola yang sudah ada kecuali ada alasan kuat untuk berbeda.
- **Pragmatis.** Tidak semua istilah teknis atau nama harus diterjemahkan jika istilah internasional lebih tepat atau sudah menjadi konvensi.
- **Layak secara teknis.** Keputusan bahasa dinilai berdasarkan semantik, implementasi, ergonomi, dan biaya pemeliharaan, bukan simbolisme semata.
- **Berkembang dengan sengaja.** Perubahan desain harus memiliki alasan, contoh, dan pertimbangan dampak.

## 2. Ruang Lingkup Bahasa

Kebijakan ini membedakan sintaks inti dari kode yang ditulis pengguna dan dari ekosistem di sekelilingnya.

| Elemen | Kebijakan |
| --- | --- |
| Keyword dan sintaks inti | Bahasa Indonesia sebagai default |
| Fungsi bawaan dan API inti | Bahasa Indonesia jika sesuai dengan desain dan konsisten |
| Nama tipe dan konsep inti | Mengikuti terminologi Nusa yang konsisten |
| Nama variabel dan fungsi buatan pengguna | Bebas mengikuti kebutuhan dan konvensi proyek |
| Komentar | Bahasa Indonesia atau bahasa lain sesuai audiens |
| Nama berkas dan direktori | Mengikuti kejelasan, konteks, dan konvensi ekosistem |
| Pustaka pihak ketiga | Mengikuti desain serta konvensi masing-masing pustaka |
| Istilah standar internasional | Dapat dipertahankan jika lebih jelas atau sudah mapan |

Identitas bahasa tidak mengharuskan setiap bagian kode menggunakan bahasa Indonesia. Tujuannya adalah konsistensi sintaks inti dan pengembangan terminologi yang terarah, bukan menerjemahkan setiap nama yang ditemui.

## 3. Sintaks dan Keyword

Keyword inti Nusa menggunakan bahasa Indonesia. Setiap keyword harus memiliki makna yang jelas, tidak tumpang tindih secara membingungkan, dan mengikuti pola sintaks yang konsisten.

Dalam merancang atau menambahkan keyword:

- Pilih istilah yang alami, ringkas, dan mudah dikenali.
- Hindari beberapa keyword untuk konsep yang sama tanpa kebutuhan yang kuat.
- Pertimbangkan keterbacaan dalam program kecil maupun kode yang lebih besar.
- Pertimbangkan konflik dengan nama yang mungkin ingin digunakan oleh programmer.
- Dokumentasikan makna, aturan penggunaan, dan contoh yang relevan.
- Pastikan perubahan sesuai dengan implementasi dan spesifikasi aktual.

Contoh seperti `fungsi`, `misalkan`, `kembalikan`, dan `cetak` hanya boleh dianggap sebagai keyword atau API resmi jika memang didukung oleh versi Nusa yang bersangkutan. Contoh dalam dokumen desain tidak dengan sendirinya menetapkan bahwa suatu sintaks telah diimplementasikan.

## 4. Penamaan dan Terminologi

Konvensi penamaan harus membantu keterbacaan tanpa membatasi cara pengguna menyusun program secara berlebihan. Nusa dapat mengembangkan istilah teknis baru yang berakar dari bahasa Indonesia, termasuk istilah yang belum dikenal secara luas, selama istilah tersebut memiliki definisi yang jelas dan digunakan secara konsisten.

- **Keyword:** mengikuti bahasa Indonesia sesuai desain inti Nusa.
- **Fungsi bawaan dan tipe inti:** mengikuti terminologi resmi Nusa.
- **Terminologi teknis Indonesia:** dapat dibentuk untuk menjelaskan konsep komputasi, arsitektur, dan komponen teknis. Kebaruan suatu istilah bukan alasan untuk menolaknya, tetapi istilah tersebut harus memiliki makna yang terdefinisi dan alasan penggunaan yang dapat dipahami.
- **Padanan internasional:** istilah teknis baru sebaiknya disertai padanan atau penjelasan bahasa Inggris apabila membantu pemahaman dan kolaborasi internasional.
- **Variabel dan fungsi buatan pengguna:** fleksibel, dengan konvensi yang dianjurkan dalam panduan gaya jika diperlukan.
- **Modul dan pustaka:** menggunakan nama yang jelas, stabil, dan sesuai konteks.
- **Nama dari pustaka eksternal:** tidak harus diterjemahkan atau diubah demi menyesuaikan bahasa Nusa.
- **Nama berkas dan direktori:** gunakan nama yang mudah dipahami dan pertahankan konvensi ekosistem yang sudah mapan bila bermanfaat.
- **Istilah internasional:** dapat dipertahankan apabila lebih tepat, lebih jelas, atau sudah menjadi konvensi yang relevan.

Istilah teknis resmi harus dibedakan dari nama internal implementasi. Tidak setiap nama modul, kelas, fungsi internal, atau komponen compiler otomatis menjadi terminologi resmi bahasa. Dokumentasi istilah teknis sebaiknya menjelaskan definisi, konteks penggunaan, dan padanan internasional yang relevan.

Nusa tidak perlu mewajibkan semua pengenal menggunakan bahasa Indonesia. Nama yang mudah dipahami dan konsisten lebih penting daripada kemurnian bahasa secara mutlak.

## 5. Komentar dan Contoh Kode

Komentar dapat ditulis dalam bahasa Indonesia atau bahasa lain sesuai audiens dan tujuan kode. Bahasa komentar tidak mengubah identitas sintaks Nusa.

Contoh ilustratif:

```nusa
# Menghitung luas persegi panjang
hitung_luas(panjang d64, lebar d64) d64 pub {
    jk panjang < 0.0 || lebar < 0.0 {
        kem -1.0 # Nilai penanda (sentinel) untuk input tidak valid
    }
    kem panjang * lebar
}
```

Versi dengan komentar untuk audiens internasional juga dapat diterima:

```nusa
# Calculate the area of a rectangle
hitung_luas(panjang d64, lebar d64) d64 pub {
    jk panjang < 0.0 || lebar < 0.0 {
        kem -1.0 # Sentinel value for invalid input
    }
    kem panjang * lebar
}
```

Contoh tersebut hanya menggambarkan kebijakan bahasa komentar. Sintaksnya harus diverifikasi terhadap versi Nusa yang benar-benar tersedia sebelum digunakan sebagai contoh dokumentasi resmi.

## 6. API, Pustaka, dan Modul

API inti Nusa sebaiknya memakai terminologi yang konsisten dengan identitas bahasanya. Namun, Nusa tidak perlu memaksakan satu pola penamaan kepada semua pustaka pihak ketiga.

Prinsipnya:

- API inti harus memiliki nama, perilaku, dan dokumentasi yang konsisten.
- Nama publik yang sudah dirilis perlu diperlakukan sebagai bagian dari pengalaman pengguna.
- Perubahan nama API harus mempertimbangkan kompatibilitas dan biaya migrasi.
- Pustaka pihak ketiga dapat mengikuti kebutuhan domain dan konvensinya sendiri.
- Konvensi impor, modul, dan struktur paket harus dijelaskan dalam dokumentasi teknis yang sesuai.
- Contoh kode harus mencerminkan API yang benar-benar tersedia.
- Istilah teknis resmi Nusa harus dibedakan dari nama internal implementasi; nama internal tidak otomatis menjadi istilah resmi.

Detail teknis mengenai sistem modul, distribusi paket, pustaka standar, dan kompatibilitas ditetapkan dalam spesifikasi atau dokumentasi implementasi terkait, bukan diasumsikan oleh dokumen ini.

## 7. Pesan Error dan Diagnostik

Pesan error Nusa sebaiknya membantu pengguna memahami masalah dan menentukan langkah berikutnya.

- Bahasa Indonesia menjadi bahasa utama untuk pesan yang ditulis khusus oleh Nusa.
- Pesan harus spesifik, jelas, dan tidak menyalahkan pengguna.
- Jika memungkinkan, tunjukkan lokasi masalah dan saran perbaikan yang relevan.
- Istilah teknis digunakan secara konsisten.
- Format diagnostik perlu mempertimbangkan tooling, editor, dan proses otomatis.
- Jika dukungan multi-bahasa ditambahkan, terjemahan tidak boleh mengubah makna teknis atau menyulitkan pencarian informasi.

Kualitas diagnostik lebih penting daripada sekadar menerjemahkan pesan. Pesan yang singkat dan tepat lebih berguna daripada pesan panjang yang hanya mengulang bahwa terjadi kesalahan.

## 8. Dokumentasi Bahasa

Dokumentasi bahasa Nusa tersedia dalam bahasa Indonesia dan Inggris sesuai kebijakan proyek.

Dokumentasi sintaks, API, dan terminologi harus menjelaskan perilaku atau makna yang sama dalam kedua bahasa. Nama keyword, istilah resmi Nusa, identifier API, contoh kode, dan hasil program tidak boleh berubah hanya karena bahasa penjelasannya berbeda.

Untuk setiap fitur atau istilah teknis yang didokumentasikan, usahakan mencakup:

- Tujuan dan perilaku fitur, atau definisi istilah.
- Bentuk sintaks atau API yang benar, jika relevan.
- Contoh yang dapat diverifikasi, jika relevan.
- Batasan, kasus khusus, dan pesan error yang relevan.
- Padanan atau penjelasan bahasa Inggris jika membantu pemahaman.
- Status dukungan pada versi Nusa yang jelas, jika berlaku.

Jangan mendokumentasikan fitur seolah sudah tersedia jika fitur tersebut masih berupa usulan atau belum didukung implementasi. Demikian pula, istilah yang masih berupa usulan tidak boleh disajikan seolah sudah menjadi terminologi resmi.

## 9. Perubahan Desain Bahasa

Perubahan pada sintaks, keyword, semantik, API inti, atau terminologi resmi harus dipertimbangkan dengan hati-hati karena dapat memengaruhi kode pengguna, dokumentasi, dan pemahaman konsep.

Sebelum perubahan besar diterapkan:

1. Jelaskan masalah atau kebutuhan yang ingin diselesaikan.
2. Tulis usulan dan contoh sebelum serta sesudah perubahan, jika relevan.
3. Pertimbangkan alternatif, konsistensi, kejelasan, dan kemudahan penggunaan.
4. Evaluasi dampak terhadap kode yang sudah ada, tooling, dan dokumentasi.
5. Catat keputusan serta alasan akhirnya.
6. Perbarui contoh dan dokumentasi yang terdampak.

Usulan terminologi baru sebaiknya menyertakan definisi, alasan pemilihan, konteks penggunaan, dan padanan internasional yang relevan. Istilah baru dapat diterima meskipun belum dikenal luas, tetapi tidak semata-mata karena keunikannya: istilah tersebut harus membantu membangun kosakata yang jelas, konsisten, dan berguna.

Perubahan yang memutus kompatibilitas perlu dinyatakan dengan jelas dan, jika memungkinkan, disertai panduan migrasi. Prosedur versi dan kebijakan kompatibilitas yang lebih rinci dapat ditetapkan dalam dokumentasi rilis atau spesifikasi bahasa.

## 10. Hal yang Tidak Menjadi Tujuan

Nusa tidak bertujuan untuk:

- Menerjemahkan setiap nama berkas, istilah, protokol, atau pustaka.
- Menganggap bahasa Indonesia otomatis membuat semua konsep pemrograman mudah.
- Mengorbankan kejelasan sintaks atau terminologi demi mempertahankan istilah tertentu.
- Menolak istilah baru hanya karena belum dikenal luas.
- Mengklaim kompatibilitas atau kemampuan yang belum diimplementasikan.
- Menyamakan preferensi bahasa dengan kualitas teknis.

Bahasa Indonesia adalah dasar identitas Nusa. Pengembangan terminologi memperkaya identitas tersebut, sedangkan kualitas desain, definisi yang jelas, dan implementasi menentukan seberapa baik istilah serta bahasa itu digunakan.

---

**Ringkasnya:** Nusa mempertahankan bahasa Indonesia pada sintaks inti dan secara sadar mengembangkan kosakata teknis yang berakar dari bahasa Indonesia. Istilah baru tidak harus sudah dikenal luas, tetapi perlu didefinisikan, digunakan secara konsisten, dan dijelaskan dengan padanan internasional jika bermanfaat. Setiap keputusan desain harus mendukung bahasa yang jelas, berguna, dan dapat dikembangkan secara berkelanjutan.