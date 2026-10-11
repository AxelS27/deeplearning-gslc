# GSLC Sesi 5

Dataset: Oxford-IIIT Pet (10 kelas: 5 ras kucing dan 5 ras anjing)

## Tugas

Tugas ini bertujuan untuk mengevaluasi efektivitas dan karakteristik transfer learning pada klasifikasi citra dalam skenario data terbatas (small-data regime). Eksperimen membandingkan 5 kondisi terstandarisasi:

1. B1 (Baseline from Scratch): ResNet-18 dengan inisialisasi bobot acak.
2. B2 (Feature Extraction): ResNet-18 pretrained ImageNet dengan backbone dibekukan penuh, hanya melatih linear classification head.
3. B3 (Progressive Fine-Tuning): ResNet-18 pretrained ImageNet dengan unfreeze parsial pada blok konvolusi teratas (layer4) dan classification head menggunakan differential learning rate.
4. B4 (Uji Kontrol Augmentasi): Konfigurasi B3 ditambah augmentasi data aktif pada data latih untuk menguji dampaknya terhadap generalization gap.
5. B5 (Arsitektur Pembanding): Konfigurasi fine-tuning terbaik diuji pada arsitektur efisien MobileNetV3-Small.

## 3 Files

Untuk meninjau kode, analisis, dan data hasil eksperimen, silakan langsung merujuk pada tiga berkas utama berikut:

1. main.ipynb  
   Jupyter Notebook utama yang memuat implementasi end to end (pipeline data, arsitektur model, training loop dengan early stopping, evaluasi, hingga visualisasi). Seluruh sel kode sudah dieksekusi lengkap beserta luaran (outputs).

2. report.pdf  
   Laporan teknis formal komprehensif yang memuat jawaban analisis konseptual (Bagian A), metodologi eksperimen (Bagian B), serta pembahasan komparatif mendalam dan analisis kegagalan (failure analysis) 8 kasus misklasifikasi teratas (Bagian C).

3. metrics.csv  
   Log data mentah hasil pelatihan per-epoch untuk seluruh eksperimen B1 s.d. B5, mencakup loss, akurasi, Macro F1 (train/val/test), waktu komputasi, serta jumlah parameter model.