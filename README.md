# Deteksi Cacat PCB Multi-Modal untuk Optimasi Produksi Elektronik: Integrasi Data Tabular SPI dan Pengenalan Citra Berbasis AI

## Deskripsi
Di era Industri 4.0, kualitas dan efisiensi produksi Printed Circuit Board (PCB) merupakan faktor penentu daya saing. Proses manufaktur PCB seringkali menghadapi tantangan dalam mendeteksi cacat, yang dapat menyebabkan kerugian signifikan. Untuk mengatasi ini, proyek ini mengembangkan model Machine Learning hibrida yang mampu menganalisis dan mengklasifikasikan PCB hasil manufaktur. Model ini mengidentifikasi tiga kategori utama: layak untuk tahap selanjutnya, rusak minor namun bisa diperbaiki, dan tidak layak/tidak bisa diperbaiki.

Tujuan utamanya adalah meningkatkan efisiensi proses manufaktur PCB dan mendukung Industri 4.0 dengan memberikan insight operasional yang memungkinkan pengambilan keputusan bisnis yang cepat dan tepat. Kami menggunakan dua sumber data real-world: data tabular dari organisasi PHME bekerja sama dengan Bitron Spa, serta data citra dari dataset "PCB Defect" Kaggle untuk pengembangan model berbasis image recognition.

Melalui pendekatan multi-modal ini—menggabungkan data inspeksi tabular dan visual—kami berupaya tidak hanya meningkatkan akurasi deteksi cacat, tetapi juga mengoptimalkan alur kerja dan efisiensi produksi. Proyek ini menghadapi beberapa tantangan teknis, seperti ketidakseimbangan kelas target (class imbalance) dan kardinalitas tinggi pada fitur kategorikal yang melekat pada data industri riil.

## Tautan Proyek
Anda bisa mengakses komponen utama proyek ini melalui tautan berikut:

Dataset: https://huggingface.co/datasets/joshedwardddd/Dataset_LG01

Model: https://huggingface.co/joshedwardddd/Model_LG01

Kode (Repositori GitHub): https://github.com/joshedwardd/Datathon2025-LG01

## Instalasi
Untuk menjalankan proyek ini secara lokal, ikuti langkah-langkah mudah berikut:

1. Kloning Repositori
Pertama, unduh kode proyek ini ke komputer Anda. Buka terminal atau Command Prompt, lalu jalankan perintah ini:

git clone https://github.com/joshedwardd/Datathon2025-LG01.git
cd Datathon2025-LG01

2. Buat Lingkungan Virtual (Direkomendasikan)
Ini akan mengisolasi dependensi proyek Anda dari instalasi Python global, menghindari konflik.

python -m venv venv

Setelah itu, aktifkan lingkungan virtual:

-Untuk Linux/macOS:

source venv/bin/activate

-Untuk Windows:

.\venv\Scripts\activate

3. Instal Dependensi
Dengan lingkungan virtual aktif, instal semua pustaka Python yang diperlukan dari requirements.txt:

pip install -r requirements.txt

4. Unduh Dataset dan Model
Dataset dan model terlatih sudah tersedia di Hugging Face. Anda bisa mengunduhnya secara manual. Pastikan file-file ini ditempatkan di direktori data/raw/ (untuk dataset) dan models/ (untuk model) sesuai struktur proyek.

Dataset: https://huggingface.co/datasets/joshedwardddd/Dataset_LG01

Model: https://huggingface.co/joshedwardddd/Model_LG01



## Cara Menjalankan Proyek
...

## Persiapan Data Umum
...


# File Proyek
# 1. Deteksi Cacat PCB berbasis Data Tabular

## 1.1 Prediksi Dini Cacat Komponen Berdasarkan Inspeksi SPI (Tahap 1)
File : Code_ModelTask1_TabularBasedDetection_LG01.ipynb

## 1.2 Prediksi Penilaian Operator Menggunakan Perbandingan Model (Tahap 2)
File : Code_ModelTask2_TabularBasedDetection_LG01.ipynb

## 1.3 Prediksi Klasifikasi Label Perbaikan (Tahap 3)
File : Code_ModelTask3_TabularBasedDetection_LG01.ipynb

# 2. Deteksi Cacat PCB berbasis Data Visual
File : Code_ImageBasedDetection_LG01.ipynb

## Hasil dan Analisis

## Kontribusi

## Kontak

## Dibuat Untuk
Proyek ini dikembangkan khusus untuk berpartisipasi dalam DATATHON 2025, sebuah kompetisi yang diselenggarakan oleh RISTEK Fasilkom Universitas Indonesia. 
