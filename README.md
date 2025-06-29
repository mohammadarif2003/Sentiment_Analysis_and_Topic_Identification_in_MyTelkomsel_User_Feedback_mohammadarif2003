# Analisis Sentimen & Identifikasi Topik pada Umpan Balik Pengguna MyTelkomsel

Proyek ini bertujuan untuk menganalisis umpan balik (ulasan) dari pengguna aplikasi MyTelkomsel untuk mengidentifikasi sentimen umum dan topik-topik utama yang menjadi keluhan. Hasil analisis ini kemudian diterjemahkan menjadi rekomendasi bisnis strategis untuk membantu Telkomsel meningkatkan kualitas layanan, kepuasan, dan loyalitas pelanggan.

## 📊 Latar Belakang & Masalah

Di tengah persaingan industri telekomunikasi yang ketat, memahami suara pelanggan secara *real-time* adalah kunci untuk mempertahankan loyalitas dan mengurangi *customer churn*. Telkomsel, sebagai salah satu pemain terbesar, menghadapi tantangan dalam mengidentifikasi masalah utama yang dikeluhkan pengguna melalui berbagai platform digital, salah satunya adalah ulasan aplikasi MyTelkomsel.

Proyek ini menjawab pertanyaan: **"Apa saja masalah utama yang dihadapi pengguna MyTelkomsel, dan bagaimana Telkomsel dapat menyelesaikannya secara strategis?"**

## 📝 Sumber Data

Data yang digunakan dalam analisis ini diperoleh melalui proses **scraping** sebanyak **5.000 ulasan terbaru** dari aplikasi MyTelkomsel di Google Play Store.

- **Tanggal Pengambilan Data: 30 Juli 2024
- **Jumlah Ulasan:** 5.000

## 🚀 Alur Kerja Proyek (Methodology)

Analisis ini dilakukan melalui beberapa tahapan utama:
1.  **Data Scraping:** Mengumpulkan ulasan teks dari Google Play Store menggunakan `google-play-scraper`.
2.  **Preprocessing Data:** Membersihkan data teks, termasuk menghapus karakter yang tidak relevan, *stopwords* (menggunakan `Sastrawi`), dan melakukan *stemming* untuk mengubah kata ke bentuk dasarnya.
3.  **Analisis Sentimen:** Melatih model klasifikasi **Naive Bayes** (`scikit-learn`) untuk mengklasifikasikan setiap ulasan ke dalam sentimen positif, negatif, atau netral.
4.  **Topic Modeling (LDA):** Menerapkan *Latent Dirichlet Allocation* (`gensim`) untuk mengidentifikasi dan mengelompokkan topik-topik utama yang paling sering dibicarakan dalam ulasan.
5.  **Analisis dan Rekomendasi Bisnis:** Menerjemahkan temuan teknis menjadi *insight* dan rekomendasi bisnis yang dapat ditindaklanjuti.

## 🛠️ Tools & Libraries

Proyek ini dibangun menggunakan **Python** dengan ekosistem data science yang kaya:

- **Data Scraping:** `google-play-scraper`
- **Manipulasi Data:** `pandas`, `numpy`
- **Text Preprocessing & NLP:** `Sastrawi` (Stemming & Stopword Removal), `nltk` (Tokenization), `re` (Regex)
- **Machine Learning & Modeling:**
  - `scikit-learn` (TF-IDF Vectorizer, Multinomial Naive Bayes, Evaluation Metrics)
  - `gensim` (Corpora, LDA Model, Coherence Score)
- **Visualisasi Data:** `matplotlib`, `seaborn`, `wordcloud`

## 💡 Temuan Utama (Key Insights)

Dari 5.000 ulasan yang dianalisis, teridentifikasi enam area masalah utama yang secara konsisten menjadi sumber ketidakpuasan pelanggan:

1.  **Kualitas Jaringan:** Keluhan dominan terkait **sinyal yang lemah dan tidak stabil**, terutama di daerah pedesaan dan bahkan beberapa area padat penduduk.
2.  **Performa Aplikasi:** Aplikasi MyTelkomsel dilaporkan **lambat, sering tidak responsif, dan mengalami *crash***, yang menyulitkan pengguna mengakses fitur esensial seperti cek kuota.
3.  **Harga Paket:** Banyak pelanggan merasa **harga paket semakin mahal** dan tidak sepadan dengan kualitas layanan yang diterima.
4.  **Pengelolaan Kuota:** Pengguna sering mengalami **gangguan teknis saat membeli paket atau mengecek sisa kuota**, yang menyebabkan frustrasi.
5.  **Layanan Pelanggan:** **Respons yang lambat** dari tim *customer support* dalam menangani keluhan teknis menjadi masalah tambahan.
6.  **Kurangnya Pemantauan Umpan Balik:** Terdapat indikasi bahwa Telkomsel belum optimal dalam memantau dan merespons keluhan pelanggan secara *real-time*.

## 🎯 Rekomendasi Strategis untuk Telkomsel

Berdasarkan temuan di atas, berikut adalah tabel rekomendasi solusi bisnis yang terfokus pada area perbaikan utama.

| **Topik Keluhan Utama** | **Area Fokus** | **Masalah Spesifik** | **Rekomendasi Solusi Bisnis** |
| :--- | :--- | :--- | :--- |
| **Kualitas Jaringan** | Infrastruktur & Jaringan | Sinyal buruk dan tidak stabil, terutama di luar kota besar. | 1. **Investasi Ekspansi Infrastruktur** di area dengan keluhan sinyal tertinggi.<br> 2. **Peningkatan Kapasitas & Pemeliharaan Rutin** pada jaringan 4G LTE.<br> 3. **Percepatan Implementasi 5G** di pusat-pusat ekonomi. |
| **Performa Aplikasi** | Platform Digital (MyTelkomsel) | Aplikasi lambat, sering crash, dan sulit digunakan. | 1. **Optimalisasi Kinerja Aplikasi** untuk mengurangi waktu muat dan *crash rate*.<br> 2. **Redesain UI/UX** dengan fokus pada alur utama (cek kuota, beli paket).<br> 3. **Pengujian Kompatibilitas** di berbagai perangkat. |
| **Harga Paket** | Produk & Harga | Harga dianggap mahal dan tidak sepadan dengan kualitas. | 1. **Evaluasi Ulang Struktur Harga** untuk menawarkan nilai yang lebih kompetitif.<br> 2. Ciptakan **Paket Fleksibel** yang dapat disesuaikan oleh pengguna.<br> 3. Kembangkan **Program Loyalitas** yang memberikan *reward* nyata. |
| **Pengelolaan Kuota & Paket** | Sistem Backend | Gagal atau lambat saat membeli paket dan mengecek kuota. | 1. **Perbaikan Stabilitas Sistem Backend** untuk transaksi yang lebih andal.<br> 2. Tambahkan **Notifikasi Proaktif** saat kuota mendekati habis.<br> 3. Sederhanakan proses pembelian menjadi lebih sedikit langkah. |
| **Layanan Pelanggan** | Customer Support | Respon lambat dalam menangani keluhan teknis. | 1. Implementasikan **Chatbot AI Cerdas** untuk menangani pertanyaan umum 24/7.<br> 2. Buat **Sistem Eskalasi Otomatis** untuk keluhan mendesak.<br> 3. Berdayakan tim support dengan akses data yang lebih baik. |
| **Pemantauan Umpan Balik** | Strategi Data | Respons reaktif terhadap keluhan pelanggan. | 1. Bangun **Dashboard Pemantauan Sentimen Real-time**.<br> 2. Ciptakan **Sistem Feedback Loop** di mana insight dari data langsung diteruskan ke tim produk dan jaringan untuk perbaikan berkelanjutan. |

## 🚀 Cara Menjalankan Kode

1.  **Kloning Repositori**:
    ```bash
    git clone https://github.com/mohammadarif2003/Sentiment_Analysis_and_Topic_Identification_in_MyTelkomsel_User_Feedback_mohammadarif2003.git
    cd Sentiment_Analysis_and_Topic_Identification_in_MyTelkomsel_User_Feedback_mohammadarif2003
    ```
2.  **Instalasi Dependensi**:
    Cara terbaik adalah dengan membuat file `requirements.txt` yang berisi semua library yang dibutuhkan, lalu jalankan:
    ```bash
    pip install -r requirements.txt
    ```
    Atau, install library secara manual:
    ```bash
    pip install pandas numpy matplotlib seaborn wordcloud google-play-scraper Sastrawi scikit-learn gensim nltk
    ```
3.  **Download NLTK Data**:
    Jalankan Python dan ketik perintah berikut untuk mengunduh tokenizer `punkt`:
    ```python
    import nltk
    nltk.download('punkt')
    ```
4.  **Jalankan Notebook**:
    Buka dan jalankan file `.ipynb` yang ada di repositori ini menggunakan Jupyter Notebook atau Google Colab.
