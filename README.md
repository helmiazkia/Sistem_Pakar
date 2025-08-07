Ini adalah sistem pakar berbasis web yang dirancang untuk membantu pengguna melakukan deteksi dini terhadap penyakit neurologis (gangguan saraf) berdasarkan gejala yang dirasakan. Sistem ini tidak menggantikan diagnosa dokter, tetapi dapat digunakan sebagai alat bantu edukasi awal.

🔧 Teknologi yang Digunakan
HTML5: Untuk struktur halaman web.

Tailwind CSS + Bootstrap 5: Untuk tampilan (UI) yang modern dan responsif.

JavaScript murni: Untuk logika diagnosa dan interaksi pengguna (tanpa framework tambahan).

🖼️ Struktur Halaman

1. Landing Page (Home)
   Bagian awal yang memperkenalkan sistem.

Terdapat tombol "Mulai Diagnosa" yang men-scroll langsung ke bagian formulir diagnosa.

2. Tentang Sistem
   Menjelaskan bahwa sistem ini berbasis rule-based (aturan) dengan bobot gejala.

Penekanan bahwa ini bukan pengganti diagnosis medis profesional.

3. Form Diagnosa
   Pengguna diberikan daftar checkbox gejala.

Setiap gejala memiliki atribut data-weight (bobot) yang mewakili tingkat signifikansinya terhadap penyakit tertentu.

Tombol:

Lihat Hasil Diagnosa → Mengolah gejala dan menampilkan kemungkinan penyakit.

Reset → Menghapus semua input dan hasil.

4. Hasil Diagnosa
   Ditampilkan jika sistem berhasil menemukan penyakit yang sesuai.

Menampilkan:

Nama penyakit

Persentase keyakinan

Penjelasan penyakit

Saran atau langkah selanjutnya

Jika tidak ada kecocokan, ditampilkan pesan peringatan.

5. Riwayat Diagnosa
   Menampilkan daftar hasil diagnosa sebelumnya secara dinamis (di-refresh setiap submit).

Tidak menggunakan database; hanya ditampilkan selama sesi aktif.

6. Footer
   Penutup halaman yang menyebutkan bahwa aplikasi ini dibuat untuk tugas kuliah AI tahun 2025.

🧮 Logika Diagnosa (JavaScript)
Penyakit dan Gejala:
Disimpan dalam array penyakitRules, masing-masing penyakit memiliki:

nama: Nama penyakit (mis. Stroke, Epilepsi)

gejala: Daftar kode gejala yang menjadi ciri penyakit itu

penjelasan: Informasi tentang penyakit

saran: Saran penanganan awal

Proses Diagnosa:
Saat form disubmit:

Semua gejala yang diceklis diambil.

Bobot masing-masing gejala dihitung.

Skor dihitung:

js
Copy
Edit
skor = (totalBobotCocok / jumlahGejalaPenyakit) \* 100
Jika skor >= 50%, maka penyakit ditampilkan sebagai hasil.

Hasil diurutkan dari skor tertinggi ke terendah.

✅ Kelebihan Program
UI responsif dan menarik dengan kombinasi Tailwind + Bootstrap.

Menggunakan pendekatan rule-based yang sederhana namun efektif.

Cocok untuk tugas akhir atau praktikum AI/Sistem Pakar.

Tidak perlu backend, bisa dijalankan langsung dari file HTML lokal.

⚠️ Catatan & Keterbatasan
Tidak menyimpan data secara permanen (riwayat hanya muncul di sesi aktif).

Tidak menggunakan inference engine seperti forward chaining/backward chaining, hanya pencocokan bobot manual.

Skalabilitas terbatas jika ingin menambahkan banyak penyakit atau gejala.

Tidak mendukung login/multi user atau rekam medis.

💡 Saran Pengembangan Lanjutan
Jika ingin dikembangkan lebih lanjut:

Tambahkan penyimpanan lokal (localStorage) atau backend (PHP, Laravel, Firebase).

Gunakan rule engine atau framework seperti CLIPS / Jess.

Tambahkan fitur grafik hasil atau riwayat dalam tabel.

Buat versi mobile app dengan Flutter/React Native.
