# VOSviewer JSON Node Remover

Sebuah *tool* interaktif berbasis Python di Google Colab untuk menghapus *term* (node) yang tidak relevan dari file JSON VOSviewer secara instan, tanpa merusak struktur data jaringan.

**Deskripsi Singkat:**
*Tool* praktis untuk membersihkan *term* yang tidak diinginkan dari file ekspor JSON VOSviewer, sehingga Anda tidak perlu mengulang pembuatan *map* bibliometrik dari awal setelah data divisualisasikan.

---

## 💡 Kenapa Tool Ini Dibuat? (Latar Belakang Masalah)

Pernahkah Anda selesai melakukan *text mining*, menunggu *loading* data yang lama, dan memvisualisasikan data di VOSviewer, lalu baru menyadari ada kata-kata umum yang tidak relevan (seperti "article", "study", "paper") ikut muncul di dalam *map*?

Jika harus mengulang proses dari awal (*Create Map* ➡️ *Extract Data* ➡️ *Select Terms*), tentu akan sangat melelahkan dan membuang banyak waktu, terutama jika dataset yang digunakan sangat besar (misalnya ribuan artikel tentang otomasi perpustakaan).

**Solusi "Anti-Capek" dengan Tool Ini:**
Daripada mengulang dari awal, Anda cukup mengekspor *map* yang sudah jadi ke format JSON, menghapus *term* yang mengganggu menggunakan program ini, dan mengimpornya kembali ke VOSviewer. Visualisasi Anda akan langsung bersih seketika!

---

## ✨ Fitur Utama

- **Interactive UI (User Interface):** Menggunakan `ipywidgets` untuk antarmuka yang intuitif langsung di dalam Google Colab.
- **Multi-Selection:** Mendukung pemilihan banyak *term* sekaligus untuk dihapus (menggunakan tombol `CTRL` atau `COMMAND`).
- **Smart Deletion (Penghapusan Pintar):** Tidak hanya menghapus *term* (node), tetapi juga secara otomatis memfilter dan menghapus garis penghubung (link/edge) yang terkait dengan *term* tersebut untuk mencegah *error*/krusial pada visualisasi.
- **Auto-Download:** File JSON yang sudah dibersihkan otomatis diunduh ke perangkat Anda dengan nama `map_vosviewer_edited.json`.

---

## 🚀 Cara Penggunaan

### Tahap 1: Ekspor Data dari VOSviewer
1. Buka *map* Anda yang sudah tervisualisasi di VOSviewer.
2. Pada panel sebelah kanan, pergi ke tab **Save**.
3. Di bagian *Network*, klik **Save...** pada opsi **VOSviewer JSON network file**.
4. Simpan file `.json` tersebut di komputer Anda.

### Tahap 2: Pembersihan Node dengan Tool Ini
1. Buka *script* ini menggunakan **Google Colab**.
2. Jalankan cell kode (tekan tombol *Play* atau `Shift + Enter`).
3. Pada antarmuka yang muncul di bawah cell:
   - Klik **1. Upload JSON** dan pilih file yang tadi diekspor dari VOSviewer.
   - Klik **Load Data**.
4. Daftar *term* akan muncul. Pilih *term* yang ingin Anda hapus (Tahan `CTRL` di Windows atau `COMMAND` di Mac untuk memilih banyak *term* sekaligus).
5. Klik tombol merah **2. Hapus & Download**.
6. Program akan memproses data dan otomatis mengunduh file baru bernama `map_vosviewer_edited.json`.

### Tahap 3: Buka Kembali di VOSviewer
1. Kembali ke aplikasi VOSviewer.
2. Pada panel sebelah kanan, pergi ke tab **Open**.
3. Di bagian *Network*, klik **Open...** pada opsi **VOSviewer JSON network file** dan pilih file `map_vosviewer_edited.json` yang baru saja diunduh.
4. Selesai! Visualisasi jaringan Anda kini sudah bersih dari *term* yang tidak relevan.

---

## 🛠️ Persyaratan & Dependencies

- Akun Google (untuk menjalankan Google Colab).
- `json` (Standard Python library)
- `ipywidgets`
- `IPython.display`
- `google.colab`
