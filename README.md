# Contoh-Kasus-Pipeline-Procesing
 Contoh Kasus: Analisis Sentimen dari Kumpulan Ulasan Produk
Misalnya kita punya dataset berisi ulasan pelanggan dari sebuah toko online, dan kita ingin mengetahui apakah ulasan tersebut bernada positif, netral, atau negatif.

🧱 Tahapan Pipeline Processing:

-Input Data
Sumber: CSV file berisi kolom review_text
Contoh isi:
"Produk ini sangat bagus, pengiriman cepat."

-Preprocessing Teks
Tokenisasi
Lowercasing (semua huruf kecil)
Hapus tanda baca
Hapus stopwords

-Ekstraksi Fitur
TF-IDF Vectorizer (mengubah teks menjadi angka)

-Klasifikasi
Model ML (misalnya: Naive Bayes, SVM, atau BERT)
Output: label sentimen (positif, negatif, netral)

-Output / Penyimpanan Hasil
Menambahkan kolom sentiment ke CSV
Menyimpan hasil ke database atau file

🧠 Ilustrasi Proses Pipeline
csharp
Salin
Edit
[Data Ulasan] 
     ↓
[Preprocessing Teks] 
     ↓
[TF-IDF Vectorizer] 
     ↓
[Model Klasifikasi Sentimen] 
     ↓
[Output: Label Sentimen]

🛠️ Contoh Nyata: Python (dengan Scikit-learn)
python
Salin
Edit
from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.naive_bayes import MultinomialNB

# Contoh data
texts = ["Saya sangat puas dengan produk ini", "Pengiriman lama dan produk rusak"]
labels = ["positif", "negatif"]

# Buat pipeline
text_clf = Pipeline([
    ('tfidf', TfidfVectorizer()),
    ('clf', MultinomialNB()),
])

# Training
text_clf.fit(texts, labels)

# Prediksi
prediksi = text_clf.predict(["Barang bagus dan murah"])
print(prediksi)
