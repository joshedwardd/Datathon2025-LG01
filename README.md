# Deteksi Cacat PCB Multi-Modal untuk Optimasi Produksi Elektronik: Integrasi Data Tabular SPI dan Pengenalan Citra Berbasis AI

## Deskripsi
Di era Industri 4.0, kualitas dan efisiensi produksi Printed Circuit Board (PCB) merupakan faktor penentu daya saing. Proses manufaktur PCB seringkali menghadapi tantangan dalam mendeteksi cacat, yang dapat menyebabkan kerugian signifikan. Untuk mengatasi ini, proyek ini mengembangkan model Machine Learning hibrida yang mampu menganalisis dan mengklasifikasikan PCB hasil manufaktur. Model ini mengidentifikasi tiga kategori utama: layak untuk tahap selanjutnya, rusak minor namun bisa diperbaiki, dan tidak layak/tidak bisa diperbaiki.

Tujuan utamanya adalah meningkatkan efisiensi proses manufaktur PCB dan mendukung Industri 4.0 dengan memberikan insight operasional yang memungkinkan pengambilan keputusan bisnis yang cepat dan tepat. Kami menggunakan dua sumber data real-world: data tabular dari organisasi PHME bekerja sama dengan Bitron Spa, serta data citra dari dataset "PCB Defect" Kaggle untuk pengembangan model berbasis image recognition.

Melalui pendekatan multi-modal ini—menggabungkan data inspeksi tabular dan visual—kami berupaya tidak hanya meningkatkan akurasi deteksi cacat, tetapi juga mengoptimalkan alur kerja dan efisiensi produksi. Proyek ini menghadapi beberapa tantangan teknis, seperti ketidakseimbangan kelas target (class imbalance) dan kardinalitas tinggi pada fitur kategorikal yang melekat pada data industri riil.

## Instalasi



## Cara Menjalankan Proyek
Bagian ini menjelaskan secara rinci langkah-langkah untuk menjalankan setiap bagian dari proyek Anda.

## Persiapan Data Umum
Jika ada langkah persiapan data yang berlaku untuk semua atau beberapa task.



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
