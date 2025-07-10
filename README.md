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
Untuk menjalankan proyek ini secara lokal, ikuti langkah-langkah berikut:

Kloning Repositori:

Bash

git clone https://github.com/joshedwardd/Datathon2025-LG01.git
cd Datathon2025-LG01
Buat Lingkungan Virtual (Direkomendasikan):
Menggunakan lingkungan virtual membantu mengisolasi dependensi proyek dari instalasi Python global Anda.

Bash

python -m venv venv
Kemudian, aktifkan lingkungan virtual tersebut:

Untuk Linux/macOS:

Bash

source venv/bin/activate
Untuk Windows:

Bash

.\venv\Scripts\activate
Instal Dependensi:
Setelah lingkungan virtual aktif, instal semua pustaka Python yang diperlukan:

Bash

pip install -r requirements.txt
Unduh Dataset dan Model:
Dataset dan model terlatih tersedia di Hugging Face. Anda bisa mengunduhnya secara manual atau menggunakan pustaka seperti huggingface_hub jika diperlukan skrip otomatis. Pastikan file-file ini ditempatkan di direktori data/raw/ dan models/ sesuai struktur proyek.

Dataset: https://huggingface.co/datasets/joshedwardddd/Dataset_LG01

Model: https://huggingface.co/joshedwardddd/Model_LG01

Tips: Jika Anda memiliki skrip Python untuk mengunduh ini secara otomatis, sebutkan di sini (misalnya, python src/download_assets.py).

Persiapan Lingkungan Tambahan (Opsional):
Untuk performa terbaik model image recognition, pastikan driver GPU NVIDIA serta CUDA Toolkit dan cuDNN Anda terinstal dan terkonfigurasi dengan benar jika Anda berencana menggunakan GPU.

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
