# 🧠 Sentiment Analysis Aplikasi (Google Play Store Reviews)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.13-orange)
![Keras](https://img.shields.io/badge/Keras-2.13-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

> Analisis sentimen berbasis **Deep Learning (BiLSTM)** terhadap ulasan pengguna **salah satu aplikasi** di **Google Play Store**.  
> Proyek ini merupakan submission resmi dalam bidang **Analisis Sentimen Multikelas (positif, netral, negatif)** menggunakan **Word2Vec** dan **TF-IDF** sebagai representasi fitur.

---

## 📘 Ringkasan Proyek

Proyek ini bertujuan untuk **mengklasifikasikan sentimen pengguna** aplikasi ke dalam tiga kategori:
- 💚 **Positif**
- 😐 **Netral**
- 💢 **Negatif**

Model dikembangkan menggunakan **Bidirectional Long Short-Term Memory (BiLSTM)** — varian dari LSTM yang unggul dalam memahami konteks dua arah pada teks berurutan.

---

## 🚀 Pipeline dan Metodologi

### 🗂️ 1. Pengumpulan Data
- Data dikumpulkan secara **mandiri (self-scraped)** menggunakan library [`google-play-scraper`](https://pypi.org/project/google-play-scraper/).  
- Dataset terdiri dari **13.428 ulasan valid** pengguna aplikasi.  
- Dataset dikategorikan ke dalam tiga kelas sentimen: *positif*, *netral*, dan *negatif*.

### 🏷️ 2. Pelabelan & Ekstraksi Fitur
- Pelabelan dilakukan menggunakan **pendekatan lexicon-based** (berdasarkan jumlah kata positif dan negatif).  
- Fitur teks diekstraksi menggunakan dua pendekatan:
  - ⚙️ **Word2Vec** – representasi semantik antar kata  
  - 🧩 **TF-IDF** – representasi berbasis frekuensi term  

### 🧠 3. Pelatihan Model (Deep Learning)
Model utama: **Bidirectional LSTM (BiLSTM)** menggunakan TensorFlow dan Keras.  
Tiga skema pelatihan dilakukan untuk evaluasi performa model:

| Skema | Algoritma | Ekstraksi Fitur | Split Data | Akurasi Training | Akurasi Testing |
|-------|------------|----------------|-------------|------------------|----------------|
| 1 | BiLSTM | Word2Vec | 80/20 | 98.27% | **95.09%** |
| 2 | BiLSTM | TF-IDF | 80/20 | 86.41% | **84.51%** |
| 3 | BiLSTM | Word2Vec | 70/30 | 97.66% | **93.92%** |

> 🔍 Dua dari tiga skema mencapai akurasi testing di atas 92%, menandakan model memiliki stabilitas dan generalisasi yang baik.
