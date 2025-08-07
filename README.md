# 🧠 Sistem Pakar Diagnosa Penyakit Neurologis

Sistem ini merupakan aplikasi **pakar berbasis web** yang dirancang untuk membantu pengguna melakukan **deteksi dini terhadap penyakit neurologis** (gangguan saraf) berdasarkan **gejala yang dirasakan**.  
Sistem ini **tidak menggantikan diagnosa dokter**, namun dapat menjadi **alat bantu edukatif awal**.

🌐 **Demo Online**: [https://diagnosapenyakit.vercel.app](https://diagnosapenyakit.vercel.app)

---

## 🔧 Teknologi yang Digunakan

- **HTML5**: Struktur halaman
- **Tailwind CSS** + **Bootstrap 5**: UI modern, cepat, dan responsif
- **JavaScript murni**: Logika sistem pakar dan interaksi pengguna
- ⚠️ _Tanpa backend dan database — sistem sepenuhnya berjalan di sisi klien (client-side only)_

---

## 🖼️ Struktur Halaman

### 1. **Landing Page (Home)**

- Bagian awal dengan judul dan pengantar sistem
- Tombol _"Mulai Diagnosa"_ untuk scroll ke bagian formulir

### 2. **Tentang Sistem**

- Menjelaskan metode diagnosa berbasis _rule-based_ dan bobot gejala
- Ditekankan bahwa sistem hanya sebagai alat bantu, bukan alat diagnosis resmi

### 3. **Form Diagnosa**

- Checklist gejala dengan bobot (`data-weight`)
- Tombol aksi:
  - `Lihat Hasil Diagnosa`: Proses perhitungan dan tampilkan hasil
  - `Reset`: Bersihkan form dan hasil sebelumnya

### 4. **Hasil Diagnosa**

- Menampilkan daftar penyakit yang cocok:
  - Nama penyakit
  - Persentase keyakinan (%)
  - Penjelasan singkat
  - Saran atau rekomendasi

### 5. **Riwayat Diagnosa**

- Menampilkan daftar penyakit dari sesi diagnosa sebelumnya
- ⚠️ Hanya disimpan sementara selama halaman aktif (tanpa database)

### 6. **Footer**

- Keterangan bahwa sistem dibuat untuk tugas kuliah AI tahun 2025

---

## 🧮 Logika Diagnosa

### Penyakit yang Dideteksi:

Disimpan dalam array `penyakitRules`:

```js
{
  nama: "Stroke",
  gejala: ["kelemahan_satu_sisi", "kehilangan_keseimbangan", "bicara_tidak_jelas"],
  penjelasan: "...",
  saran: "..."
}
```
