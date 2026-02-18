# VOSviewer JSON Editor - Hapus Term Tanpa Visualisasi Ulang

Tool untuk mengedit file JSON hasil export VOSviewer tanpa perlu memulai visualisasi dari awal. Cocok ketika Anda sudah terlanjur membuat visualisasi tapi ingin menghapus beberapa term yang tidak diperlukan.

## 🎯 Latar Belakang

Pernah mengalami situasi ini?
- Sudah cape-cape bikin visualisasi VOSviewer, tapi ternyata ada beberapa term yang tidak relevan
- Males ngulang dari awal karena proses filtering dan settingnya ribet
- Tapi tetap ingin menghapus term-term tersebut beserta koneksinya

**Nah, tool ini solusinya!** Cukup upload file JSON hasil export VOSviewer, pilih term yang ingin dihapus, dan dapatkan file JSON baru yang sudah teredit.

## 📋 Deskripsi

Tool ini memungkinkan Anda untuk:
- Memuat file JSON hasil visualisasi VOSviewer yang sudah jadi
- Melihat daftar semua term yang ada
- Memilih satu atau banyak term untuk dihapus
- Secara otomatis menghapus semua link yang terhubung dengan term tersebut
- Mendownload file JSON baru yang siap digunakan kembali

**Tanpa perlu memulai visualisasi dari awal!**

## 🚀 Cara Penggunaan

### Langkah 1: Export File dari VOSviewer
1. Buka visualisasi VOSviewer Anda yang sudah jadi
2. Export ke format JSON (File > Export > Create Map File)
3. Simpan file JSON tersebut

### Langkah 2: Upload ke Google Colab
1. Buka notebook ini di Google Colab
2. Jalankan semua sel (Runtime > Run all)
3. Klik tombol "1. Upload JSON" dan pilih file Anda
4. Klik "Load Data"

### Langkah 3: Pilih Term yang Ingin Dihapus
- Akan muncul daftar semua term dalam visualisasi Anda
- Pilih term yang tidak diinginkan (gunakan CTRL/COMMAND untuk multi-select)
- Term yang dipilih akan dihapus beserta seluruh garis penghubungnya

### Langkah 4: Download Hasil
- Klik tombol merah "2. Hapus & Download"
- File baru `map_vosviewer_edited.json` otomatis terdownload
- Upload file ini ke VOSviewer dan visualisasi Anda sudah siap tanpa term-term yang tidak diinginkan

## 💡 Contoh Kasus

**Visualisasi Awal:**
- 200 term hasil analisis bibliometric
- Ternyata ada 10 term yang tidak relevan (misalnya kata umum seperti "study", "research")

**Dengan tool ini:**
1. Cukup hapus 10 term tersebut
2. Link ke term lain otomatis terhapus
3. Visualisasi tetap utuh untuk 190 term sisanya
4. **Tidak perlu mengulang proses filtering dari awal!**

## ✨ Keuntungan

- ✅ **Hemat waktu** - Tidak perlu setting ulang threshold, scoring method, dll
- ✅ **Presisi** - Hanya menghapus term yang memang tidak diinginkan
- ✅ **Mudah** - Interface sederhana dengan multi-select
- ✅ **Aman** - File asli tetap terjaga, selalu bisa upload ulang jika salah pilih

## ⚙️ Fitur Detail

- **Multi-select term**: Pilih banyak term sekaligus
- **Auto-delete links**: Semua koneksi ke term yang dihapus ikut terhapus
- **Link integrity**: Link antar term yang tersisa tetap utuh
- **Instant download**: File langsung terdownload setelah proses selesai
- **Informasi proses**: Tampilkan jumlah term dan link yang dihapus

## 📊 Perbandingan

| Tanpa Tool Ini | Dengan Tool Ini |
|----------------|-----------------|
| Harus visualisasi ulang dari awal | Edit file JSON langsung |
| Setting parameter ulang (threshold, dll) | Parameter visualisasi tetap |
| Butuh waktu 5-15 menit | Hanya 1-2 menit |
| Bisa lupa setting awal | Setting awal tetap terjaga |

## 🔧 Teknis

- Dibuat untuk Google Colab (menggunakan `files.upload()` dan `files.download()`)
- Menggunakan ipywidgets untuk interface interaktif
- Mempertahankan struktur asli JSON VOSviewer
- Hanya memodifikasi bagian `items` dan `links`

## 📝 Tips Penggunaan

1. **Backup file asli** - Meskipun aman, tetap simpan file asli Anda
2. **Selektif memilih** - Gunakan multi-select untuk efisiensi
3. **Cek hasil** - Buka file hasil di VOSviewer untuk memastikan visualisasi sesuai harapan

## ❓ Troubleshooting

**Q: File tidak bisa diupload?**
A: Pastikan file berformat .json dan merupakan hasil export VOSviewer yang valid

**Q: Kok tidak ada term yang muncul?**
A: Periksa struktur JSON, harus memiliki key `network.items`

**Q: Salah hapus term?**
A: Upload ulang file asli dan ulangi proses

## 🤖 Tentang Pengembangan
**Dikembangkan dengan bantuan Google Gemini 3.5 Pro**
