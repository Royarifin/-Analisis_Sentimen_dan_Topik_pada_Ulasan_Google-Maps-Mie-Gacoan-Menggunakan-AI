# Analisis_Sentimen_dan_Topik_pada_Ulasan_Google-Maps-Mie-Gacoan-Menggunakan-AI
Analisis Sentimen dan Rekomendasi Strategis untuk Mie Gacoan Lampung Menggunakan AI
Sebuah Proyek Capstone oleh: [Nama Lengkap Anda]

1. Project Overview
Latar Belakang
Mie Gacoan merupakan salah satu brand F&B dengan pertumbuhan paling pesat di Indonesia, termasuk di Bandar Lampung. Popularitas ini menghasilkan volume ulasan online yang sangat tinggi di platform seperti Google Maps. Setiap ulasan ini adalah feedback berharga yang, jika diolah dengan benar, dapat menjadi kunci untuk peningkatan kualitas layanan dan kepuasan pelanggan.

Permasalahan
Manajemen menghadapi tantangan dalam memproses ribuan ulasan pelanggan yang bersifat kualitatif dan tidak terstruktur. Proses manual untuk membaca, mengkategorikan, dan menyimpulkan insight dari data ini tidak efisien, memakan waktu, dan rentan terhadap bias.

Tujuan Proyek
Proyek ini bertujuan untuk membangun sebuah alur kerja data science untuk:

Mengklasifikasikan sentimen dan area masalah dari ulasan pelanggan secara otomatis menggunakan AI (IBM Granite).

Menghasilkan insight berbasis data untuk mengidentifikasi prioritas perbaikan yang paling mendesak.

Merumuskan rekomendasi strategis yang actionable untuk meningkatkan kepuasan pelanggan dan efisiensi operasional.

2. Dataset & Tools
Sumber Data: 100 Ulasan Publik Pelanggan Mie Gacoan Lampung

Link Dataset Mentah: https://raw.githubusercontent.com/Royarifin/Analisis_Sentimen_dan_Topik_pada_Ulasan_Google-Maps-Mie-Gacoan-Menggunakan-AI/refs/heads/main/ulasan_gacoan_lampung.csv

Perangkat & Teknologi:

Bahasa & Library: Python (Pandas, Matplotlib, Seaborn, TQDM)

Lingkungan Kerja: Google Colab

Model AI: http://ibm-granite/granite-3.3-8b-instruct
Framework & API: LangChain & Replicate API

3. Analysis Process: Sebuah Pendekatan Kaizen
Proses analisis ini tidak berjalan linear, melainkan melalui serangkaian iterasi dan penyempurnaan berkelanjutan (Kaizen) untuk mengatasi setiap tantangan yang muncul.

Pembersihan & Validasi Data:

Tantangan: Dataset mentah berisi data yang tidak relevan (ulasan tanpa teks) dan memerlukan standarisasi untuk memastikan akurasi analisis.

Solusi: Sebuah skrip pembersihan otomatis diimplementasikan untuk membuang ulasan kosong dan memotong data agar tepat 100 ulasan valid yang dianalisis, memastikan integritas data.

Otomatisasi Analisis (Batch Processing):

Analisis dilakukan secara batch (kelompok kecil  5 ulasan) untuk efisiensi dan stabilitas, dengan tqdm untuk memvisualisasikan progres.

Prompt Engineering (Klasifikasi Multi-Dimensi):

Prompt AI disempurnakan untuk tidak hanya mengekstrak sentimen, tetapi juga aspek_utama, detail_masalah, dan tingkat_urgensi dari setiap ulasan. Instruksi eksplisit ditambahkan untuk menjaga konsistensi jumlah output.

Pengembangan Parser Universal:

Tantangan: Output AI ternyata tidak konsisten (terkadang list JSON [...], terkadang objek terpisah).

Solusi: Sebuah parser yang "tahan banting" dikembangkan dengan beberapa strategi (termasuk Regular Expression) untuk memastikan semua format output dapat dibaca dengan benar.

Parameter Tuning:

Parameter seperti temperature dan max_new_tokens disesuaikan secara iteratif untuk mengontrol presisi, gaya, dan panjang output AI, baik untuk klasifikasi maupun pembuatan rekomendasi.

Prompting Multi-Langkah:

Tantangan: Output laporan dari AI terpotong karena batasan model.

Solusi: Permintaan laporan dipecah menjadi beberapa bagian yang lebih kecil ("mewawancarai" AI), lalu hasilnya digabungkan untuk membentuk laporan akhir yang utuh.

4. Insight & Findings
Gambaran Umum: Mayoritas Pelanggan Tidak Puas
Visualisasi data menunjukkan adanya masalah sistemik. Sekitar 75% ulasan pelanggan bersifat negatif atau campuran, yang memerlukan perhatian segera.

Akar Masalah: Pelayanan Buruk & Kebersihan Kurang
Analisis lebih dalam menunjukkan bahwa keluhan pelanggan sangat terkonsentrasi pada dua area utama, dan sebagian besar bersifat mendesak.

Kategori Masalah: Pelayanan dan Kebersihan adalah dua area yang paling dominan dikeluhkan.

Tingkat Urgensi: Mayoritas masalah ini diklasifikasikan sebagai berurgensi 'Tinggi'.

5. Conclusion & Recommendations
Berdasarkan insight data, AI berperan sebagai konsultan strategis dan menghasilkan diagnosis serta rencana aksi berikut:

Kesimpulan & Diagnosis Masalah Inti
Tingkat Urgensi Masalah Tinggi: Sejumlah besar ulasan (47) diklasifikasikan sebagai masalah berurgensi 'Tinggi', menunjukkan adanya isu kritis yang berpotensi merusak reputasi.

Area Masalah Utama: Tiga kategori utama yang menjadi sumber keluhan pelanggan adalah Pelayanan, Kebersihan, dan Makanan.

Rencana Aksi Rekomendasi
Prioritas #1: Mengurangi Keluhan Kebersihan

Langkah Konkret:

Implementasikan prosedur kebersihan terperinci untuk semua area, terutama dining dan kasir.

Lakukan pelatihan ulang staf mengenai praktik kebersihan yang tepat dan manajemen sampah.

Jadwalkan inspeksi kebersihan berkala untuk memastikan standar dipatuhi.

Prioritas #2: Memperbaiki Pelayanan Kasir & Akurasi Pesanan

Langkah Konkret:

Buat SOP yang jelas bagi kasir untuk melakukan konfirmasi ulang (clarify) pesanan pelanggan.

Berikan pelatihan teknis tambahan kepada kasir untuk menangani pesanan kompleks dan mengurangi kesalahan.

Pertimbangkan implementasi sistem pesan online/mobile untuk mengurangi beban kasir dan kesalahan manual.

Prioritas #3: Mengurangi Waktu Tunggu & Meningkatkan Kualitas Makanan

Langkah Konkret:

Optimalkan proses di dapur untuk mempercepat waktu persiapan makanan.

Terapkan langkah Quality Control (QC) terakhir sebelum pesanan disajikan untuk memastikan konsistensi rasa dan suhu.

Proyeksi Dampak Positif
Dengan menerapkan rencana aksi di atas, diharapkan akan tercapai perubahan positif yang signifikan, meliputi peningkatan sentimen pelanggan, penurunan jumlah komplain berurgensi tinggi, serta peningkatan efisiensi operasional secara keseluruhan.

6. AI Support Explanation
Peran AI dalam proyek ini melampaui sekadar alat, melainkan sebagai mitra yang memainkan tiga peran kunci:

AI sebagai Analis Skala Besar: Melakukan klasifikasi multi-dimensi pada ratusan ulasan dalam hitungan menit, tugas yang mustahil dilakukan manual dengan efisien.

AI sebagai Problem Solver: Membantu mengatasi tantangan teknis seperti inkonsistensi data dan keterbatasan model melalui teknik prompting yang adaptif.

AI sebagai Konsultan Strategis: Menghasilkan laporan diagnosis dan rencana aksi yang terstruktur dan profesional berdasarkan insight data.
