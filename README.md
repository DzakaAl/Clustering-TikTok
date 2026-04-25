# Klasterisasi Pengguna TikTok

Project ini berisi dua tahap utama:
1. Scraping komentar TikTok menggunakan Apify.
2. Analisis dan klasterisasi komentar menggunakan NLP, TF-IDF, K-Means, dan AHC.

## Struktur Project
- scraping.ipynb: notebook untuk mengambil data komentar TikTok dan menyimpan ke CSV.
- skripsi.ipynb: notebook analisis data, preprocessing teks, clustering, visualisasi, dan evaluasi.
- Tiktok.csv: data hasil scraping komentar.
- slang_indo.csv: kamus kata gaul untuk normalisasi teks.

## Prasyarat
- Python 3.9 atau lebih baru.
- Jupyter Notebook atau VS Code dengan extension Jupyter.
- Akun Apify dan API token aktif.

## Instalasi Library
Jalankan perintah berikut di terminal:

```bash
pip install apify-client pandas numpy matplotlib scipy scikit-learn wordcloud indoNLP Sastrawi
```

## Langkah Menjalankan Scraping
Buka scraping.ipynb lalu jalankan cell dari atas ke bawah.

1. Import library.
2. Isi TOKEN_API dengan token Apify Anda.
3. Isi VIDEO_URLS dengan satu atau beberapa URL video TikTok.
4. Atur parameter scraping pada run_input.
5. Jalankan actor Apify untuk mengambil data komentar.
6. Simpan hasil ke file Tiktok.csv.

Output scraping:
- Tiktok.csv

## Langkah Menjalankan Analisis
Buka skripsi.ipynb lalu jalankan cell berurutan dari atas ke bawah.

Tahapan utama analisis:
1. Import library dan load dataset.
2. Preprocessing teks:
   - cleaning
   - case folding
   - normalisasi kata gaul
   - tokenisasi
   - stopword removal
   - stemming
3. Ekstraksi fitur TF-IDF.
4. Penentuan jumlah cluster (Elbow Method).
5. Clustering K-Means.
6. Clustering AHC (dendrogram dan pemotongan threshold).
7. Visualisasi distribusi cluster dan word cloud.
8. Evaluasi model dengan Silhouette Score dan Davies-Bouldin Index.
9. Simpan hasil akhir ke Tiktok_cluster.csv.

Output analisis:
- Tiktok_cluster.csv

## Catatan Penggunaan
- Jangan menyimpan TOKEN_API asli ke repository publik.
- Jika scraping gagal, cek kuota akun Apify, validitas token, dan format URL TikTok.
- Pastikan file Tiktok.csv tersedia sebelum menjalankan notebook analisis.

## Saran Alur Eksekusi
1. Jalankan scraping.ipynb untuk menghasilkan Tiktok.csv terbaru.
2. Jalankan skripsi.ipynb untuk proses analisis dan clustering.
3. Gunakan hasil cluster untuk interpretasi topik komentar dan pelaporan penelitian.