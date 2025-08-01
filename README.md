# 🕵️‍♂️ BOT Detection di Media Sosial - Instagram & Twitter

Proyek machine learning untuk mendeteksi akun bot pada platform Instagram dan Twitter menggunakan model berbasis machine learning. Sistem ini mampu mengklasifikasikan apakah suatu akun termasuk bot atau bukan berdasarkan fitur-fitur yang diperoleh dari data profil dan aktivitas pengguna.

## 📋 Deskripsi Project

Proyek ini bertujuan untuk membangun sistem deteksi akun bot pada media sosial berbasis data structured (numerik dan kategorikal). Dengan pendekatan supervised learning, model dilatih secara terpisah untuk data Instagram dan Twitter untuk menangani karakteristik masing-masing platform.

## 🗂️ Struktur Project

```
bot-detection-social-media/
├── 📊 data/                          # Dataset hasil crawling & prediksi
│   ├── train_ig.csv                 # Data training Instagram
│   ├── test_ig.csv                  # Data testing Instagram
│   ├── train_twitter.csv            # Data training Twitter
│   ├── test_twitter.csv             # Data testing Twitter
│   ├── test_with_predictions_IG.csv        # Hasil prediksi model IG
│   └── test_with_predictions_Twitter.csv   # Hasil prediksi model Twitter
├── 🤖 models/                        # Model terlatih
│   ├── IG_BOT_Detection_Model_v1.pkl         # Model deteksi bot Instagram
│   └── Twitter_BOT_Detection_Model_v1.pkl    # Model deteksi bot Twitter
├── 📓 notebook/                      # Jupyter notebooks untuk development
│   ├── 0_dataset.ipynb              # Proses eksplorasi dan pembersihan data
│   ├── 1_model_inspect.ipynb        # Analisis performa dan evaluasi model
│   ├── 2_dev.ipynb                  # Eksperimen dan pengujian pendekatan model
│   ├── 3_train_IG.ipynb             # Training model Instagram
│   ├── 3_train_Twitter.ipynb        # Training model Twitter
│   └── 4_fine_tune.ipynb            # Fine-tuning & optimasi akhir
└── README.md                        # Dokumentasi proyek
```

## 🚀 Instalasi dan Setup

### 1. Clone Repository

```bash
git clone <repository-url>
cd bot-detection-social-media
```

### 2. Buat Virtual Environment

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
# atau
.venv\Scripts\activate     # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

> Jika file `requirements.txt` belum ada, kamu bisa install paket seperti: `scikit-learn`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `joblib`.

## 📊 Dataset

Dataset terdiri dari dua sumber utama:

* **Instagram** (`train_ig.csv`, `test_ig.csv`)
* **Twitter** (`train_twitter.csv`, `test_twitter.csv`)

Masing-masing data berisi fitur-fitur numerik dan kategorikal akun media sosial seperti jumlah followers, following, tweet/post, engagement, dan lainnya.

Contoh fitur:

* `followers_count`
* `friends_count`
* `statuses_count`
* `favourites_count`
* `listed_count`
* dll.

Kolom target (label):

* `account_type` dan `fake`: 0 (bukan bot), 1 (bot)

## 🔬 Workflow Development

### 1. Dataset Exploration (`0_dataset.ipynb`)

* Eksplorasi awal
* Pembersihan data
* Analisis distribusi label
* Deteksi outlier dan imbalance

### 2. Model Development (`2_dev.ipynb`)

* Feature selection dan engineering
* Pemilihan algoritma awal
* Cross-validation dan metrik evaluasi

### 3. Model Training

* Instagram: `3_train_IG.ipynb`
* Twitter: `3_train_Twitter.ipynb`
* Model disimpan dalam format `.pkl`

### 4. Model Evaluation (`1_model_inspect.ipynb`)

* Confusion matrix
* Precision, Recall, F1-Score
* Visualisasi performa model

### 5. Fine-tuning (`4_fine_tune.ipynb`)

* Optimasi hyperparameter
* Pembandingan berbagai algoritma
* Penyesuaian threshold prediksi

## 🤖 Model

* **Arsitektur**: Random Forest, Gradient Boosting, XGBoost, atau sejenisnya
* **Task**: Binary Classification (Bot / Bukan Bot)
* **Output**: Probabilitas dan label prediksi
* **Format**: `.pkl` untuk integrasi mudah

## 📈 Evaluasi Model

Metrik evaluasi utama:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-Score**
* **Confusion Matrix**

Hasil prediksi akhir disimpan di:

* `test_with_predictions_IG.csv`
* `test_with_predictions_Twitter.csv`

## 💻 Contoh Penggunaan Model

```python
import pandas as pd
import joblib

# Load model
model = joblib.load('./models/IG_BOT_Detection_Model_v1.pkl')

# Load sample data
df = pd.read_csv('./data/test_ig.csv')

# Prediksi
pred = model.predict(df.drop(columns='label'))
print(pred)
```

## 🛠️ Kontribusi

1. Fork repository ini
2. Buat branch baru (`git checkout -b fitur/ModelIGv2`)
3. Commit perubahan (`git commit -m 'Train IG model v2'`)
4. Push ke branch (`git push origin fitur/ModelIGv2`)
5. Buat Pull Request

## 🐛 Pelaporan Bug & Permintaan Fitur

Silakan buka *issue* jika ada bug, pertanyaan, atau saran pengembangan baru.

## 📄 Lisensi

Project ini dilisensikan di bawah [MIT License]().

## 👥 Tim Pengembang

* **Data Scientist** – Eksplorasi data, pemodelan dan fine-tuning
* **ML Engineer** – Penanganan pipeline dan deployment model

---

**Terakhir diperbarui**: 2025-08-01
🔗 **Repository**: [bot-detection-social-media](https://github.com/NewReyy/BOT_Detection/)

---
