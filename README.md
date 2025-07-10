# Deteksi Cacat PCB Multi-Modal untuk Optimasi Produksi Elektronik: Integrasi Data Tabular SPI dan Pengenalan Citra Berbasis AI

## Deskripsi
Di era Industri 4.0, kualitas dan efisiensi produksi Printed Circuit Board (PCB) merupakan faktor penentu daya saing. Proses manufaktur PCB seringkali menghadapi tantangan dalam mendeteksi cacat, yang dapat menyebabkan kerugian signifikan. Untuk mengatasi ini, proyek ini mengembangkan model Machine Learning hibrida yang mampu menganalisis dan mengklasifikasikan PCB hasil manufaktur. Model ini mengidentifikasi tiga kategori utama: layak untuk tahap selanjutnya, rusak minor namun bisa diperbaiki, dan tidak layak/tidak bisa diperbaiki.

Tujuan utamanya adalah meningkatkan efisiensi proses manufaktur PCB dan mendukung Industri 4.0 dengan memberikan insight operasional yang memungkinkan pengambilan keputusan bisnis yang cepat dan tepat. Kami menggunakan dua sumber data real-world: data tabular dari organisasi PHME bekerja sama dengan Bitron Spa, serta data citra dari dataset "PCB Defect" Kaggle untuk pengembangan model berbasis image recognition.

Melalui pendekatan multi-modal ini—menggabungkan data inspeksi tabular dan visual—kami berupaya tidak hanya meningkatkan akurasi deteksi cacat, tetapi juga mengoptimalkan alur kerja dan efisiensi produksi. Proyek ini menghadapi beberapa tantangan teknis, seperti ketidakseimbangan kelas target (class imbalance) dan kardinalitas tinggi pada fitur kategorikal yang melekat pada data industri riil.

## Tautan Proyek
Anda bisa mengakses komponen utama proyek ini melalui tautan berikut:

    - Dataset: https://huggingface.co/datasets/joshedwardddd/Dataset_LG01

    - Model: https://huggingface.co/joshedwardddd/Model_LG01

    - Kode (Repositori GitHub): https://github.com/joshedwardd/Datathon2025-LG01

## Instalasi
Untuk menjalankan proyek ini secara lokal, ikuti langkah-langkah mudah berikut:

1. Kloning Repositori
Pertama, unduh kode proyek ini ke komputer Anda. Buka terminal atau Command Prompt, lalu jalankan perintah ini:

    - git clone https://github.com/joshedwardd/Datathon2025-LG01.git
    - cd Datathon2025-LG01

2. Buat Lingkungan Virtual (Direkomendasikan)
Ini akan mengisolasi dependensi proyek Anda dari instalasi Python global, menghindari konflik.
    - python -m venv venv

Setelah itu, aktifkan lingkungan virtual:

- Untuk Linux/macOS:

    - source venv/bin/activate

- Untuk Windows:

    - .\venv\Scripts\activate

3. Instal Dependensi
Dengan lingkungan virtual aktif, instal semua pustaka Python yang diperlukan dari requirements.txt:

    - pip install -r requirements.txt

4. Unduh Dataset dan Model
Dataset dan model terlatih sudah tersedia di Hugging Face. Anda bisa mengunduhnya secara manual. Pastikan file-file ini ditempatkan di direktori data/raw/ (untuk dataset) dan models/ (untuk model) sesuai struktur proyek.

    - Dataset: https://huggingface.co/datasets/joshedwardddd/Dataset_LG01

    - Model: https://huggingface.co/joshedwardddd/Model_LG01

# Detail Notebook Utama
Berikut adalah penjelasan lebih lanjut mengenai notebook yang memuat implementasi model kami:

## 1. Deteksi Cacat PCB Berbasis Data Tabular (Pendekatan Hirarkis Sekuensial)
Kami mengimplementasikan pipeline klasifikasi hirarkis dengan tiga model yang bekerja secara sekuensial untuk analisis data tabular:

### Exploratory Data Analysis (Data Tabular)

- File : Code_EDA_TabularBasedDetection_LG01.ipynb

- Notebook Code_EDA_TabularBasedDetection_LG01.ipynb adalah langkah fundamental dalam proyek ini. Exploratory Data Analysis (EDA) sangat penting untuk memahami karakteristik dan struktur data tabular yang kompleks, yang pada akhirnya akan memengaruhi kinerja model deteksi cacat.

### 1.1 Prediksi Dini Cacat Komponen Berdasarkan Inspeksi SPI (Tahap 1)

- File: Code_ModelTask1_TabularBasedDetection_LG01.ipynb

- Tujuan: Bertindak sebagai detektor awal (early detector). Model ini menganalisis data dari tahap awal inspeksi Solder Paste Inspection (SPI) untuk memprediksi probabilitas sebuah unit PCB (figure) dikategorikan sebagai cacat atau tidak oleh mesin Automated Optical Inspection (AOI) di akhir lini produksi.

### 1.2 Prediksi Penilaian Operator Menggunakan Perbandingan Model (Tahap 2)

- File: Code_ModelTask2_TabularBasedDetection_LG01.ipynb

- Tujuan: Jika sebuah unit PCB ditandai cacat oleh model Tahap 1, model pada Tahap 2 ini akan memprediksi penilaian operator (apakah Good atau Bad) terhadap unit cacat tersebut, secara efektif menggantikan peran operator manusia dalam proses AOI.

### 1.3 Prediksi Klasifikasi Label Perbaikan (Tahap 3)

- File: Code_ModelTask3_TabularBasedDetection_LG01.ipynb

- Tujuan: Tahap terakhir ini adalah model klasifikasi multi-kelas yang memprediksi opsi perbaikan untuk komponen yang dinilai Bad oleh operator. Model akan menentukan apakah unit tersebut masih dapat diperbaiki, sudah tidak bisa diperbaiki, atau merupakan kesalahan deteksi oleh mesin.

## 2. Deteksi Cacat PCB Berbasis Data Visual
- File: Code_ImageBasedDetection_LG01.ipynb

- Tujuan: Metode ini menggunakan pendekatan klasifikasi citra secara langsung. Model akan menganalisis gambar PCB dan mengklasifikasikannya ke dalam enam kelas cacat yang berbeda (yaitu missing hole, mouse bite, open circuit, short, spur, spurious copper) atau sebagai PCB normal.


## Hasil

## 1. Deteksi Cacat PCB Berbasis Data Tabular
Pendekatan tabular menggunakan pipeline hirarkis dengan tiga model sekuensial:

### 1.1 Prediksi Dini Cacat Komponen (Tahap 1)

- Model Terbaik: LightGBM

- Performa Kunci: Mencapai akurasi 94%. Model ini menunjukkan presisi yang sangat baik (98%) dan recall kuat (92%) untuk kelas "Defect", serta presisi 90% dan recall 97% untuk "Not Defect". LightGBM dipilih karena performanya yang seimbang dan efisiensi komputasi yang tinggi, dengan jumlah False Positive yang minimal.

### 1.2 Prediksi Penilaian Operator (Tahap 2)

- Model Terbaik: LightGBM

- Performa Kunci: Mencapai akurasi 98%. LightGBM unggul dalam memprediksi kelas "Good" dengan presisi 98% dan recall sempurna 100%. Meskipun recall untuk kelas "Bad" (61%) sedikit lebih rendah dibandingkan XGBoost, presisi (96%) dan jumlah False Positive yang minimal (hanya 3 kasus) menunjukkan kemampuannya yang andal dalam menangani ketidakseimbangan data pada tugas ini.

### 1.3 Klasifikasi Label Perbaikan (Tahap 3)

- Model Terbaik: LightGBM

Alasan Pemilihan: Terpilih karena keseimbangan performa terbaik dan efisiensi operasional. LightGBM menunjukkan F1-score macro avg tertinggi (0.76) dan F1-score terbaik (0.42) untuk kelas krusial 'FalseScrap', meskipun akurasi keseluruhannya (86%) tidak paling tinggi. Kecepatan training yang unggul juga mendukung implementasi praktis.

## 2. Deteksi Cacat PCB Berbasis Data Visual
Model Terbaik: ResNet18 (Full Fine-Tuned)

- Performa Kunci: Model ini mencapai akurasi keseluruhan 93.54% dalam mengklasifikasikan enam jenis cacat PCB (missing_hole, mouse_bite, open_circuit, short, spur, spurious_copper) atau sebagai PCB normal.

- Keunggulan: ResNet18 yang di-fine-tune penuh secara signifikan melampaui arsitektur CNN kustom dan ResNet18 standar. Keunggulannya berasal dari arsitektur residual yang kokoh, pemanfaatan transfer learning dari ImageNet, dan full fine-tuning yang mendalam pada seluruh jaringan, memungkinkannya beradaptasi secara optimal dengan detail cacat PCB yang rumit.

- Metrik Spesifik: Model ini menunjukkan recall sempurna (100%) untuk missing_hole dan spurious_copper, serta presisi tinggi (98.8%) untuk missing_hole dan 100% untuk short. Analisis confusion matrix menunjukkan jumlah kesalahan klasifikasi yang minimal, secara drastis mengurangi False Negative dan False Positive dibandingkan model lain.

## Pembuat
- Josh Edward Sutanto
- Vincentius Jacob Gunawan
- Rizky Fadhilah

## Dibuat Untuk
Proyek ini dikembangkan khusus untuk berpartisipasi dalam DATATHON 2025, sebuah kompetisi yang diselenggarakan oleh RISTEK Fasilkom Universitas Indonesia. 
