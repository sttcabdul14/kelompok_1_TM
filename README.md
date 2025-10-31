# kelompok_1_TM
Tugas tim kami _Topik Modeling_
Proyek ini merupakan tugas kelompok mata kuliah Modeling and Simulation, dengan fokus pada penerapan Topic Modeling (LDA) untuk analisis kumpulan berita pemerintahan terkini.
Penjelasan Proyek Topic Modeling Berita Pemerintah
**1. Latar Belakang**

Dalam proyek ini, kami mencoba menerapkan Topic Modeling untuk menemukan pola topik dari beberapa berita viral terkait kebijakan pemerintah Indonesia. Dengan pendekatan ini, sistem dapat mengenali topik utama yang muncul tanpa perlu diberi label terlebih dahulu.

Metode ini cocok digunakan untuk analisis teks dalam jumlah banyak, misalnya kumpulan berita, komentar publik, atau dokumen kebijakan.
**2. Dataset**
Dataset dibuat secara manual dari beberapa berita terkini yang diambil dari situs seperti Kompas.com dan Detik.com.
Kami menggunakan 5 berita singkat tentang topik pemerintahan seperti:

Kenaikan harga BBM
Ibu Kota Nusantara (IKN)
Subsidi energi
Harga beras
Bantuan sosial (Bansos)

Dataset disimpan dalam bentuk tabel (DataFrame) dengan dua kolom utama:
judul → judul berita
isi → isi singkat dari berita tersebut

**3. Preprocessing (Pembersihan Teks)**
Sebelum pemodelan, teks dibersihkan agar komputer lebih mudah mengenali makna kata.
Langkah-langkah preprocessing yang kami lakukan:

Mengubah teks menjadi huruf kecil (lowercase)
Menghapus angka, tanda baca, dan simbol
Melakukan tokenisasi (memecah kalimat jadi kata)
Menghapus stopwords Bahasa Indonesia (kata umum seperti “yang”, “dan”, “di”) menggunakan nltk.corpus.stopwords

Hasilnya disimpan di kolom baru bernama clean_text.
CONTOH : pemerintah berencana naikkan harga bbm awal bulan depan karena kenaikan harga minyak dunia
**4. Topic Modeling (Pemodelan Topik)**

Kami menggunakan algoritma Latent Dirichlet Allocation (LDA) dari library scikit-learn.
Tahapan proses:

Mengubah teks menjadi representasi angka dengan CountVectorizer
- setiap kata dihitung frekuensinya di seluruh dokumen.
Menentukan jumlah topik (n_components=2)
- misalnya kami ingin model membagi kumpulan berita menjadi 2 topik utama.

Melatih model LDA untuk mencari kelompok kata yang sering muncul bersama.
Dengan kode utama : lda_model = LatentDirichletAllocation(n_components=2, random_state=42)
lda_model.fit(X)

**5. Hasil dan Interpretasi**

Hasil pemodelan menampilkan kata-kata paling berpengaruh di setiap topik.
HASILNYA : 
Topik 1=
bbm, harga, minyak, subsidi, energi

Topik 2=
presiden, ikn, pembangunan, bansos, keluarga
**6. Kesimpulan**

Proyek ini menunjukkan bahwa dengan LDA, kita dapat:
-Mengelompokkan teks berita berdasarkan kemiripan makna.
-Mengidentifikasi topik utama dalam kumpulan berita tanpa label.
-Menerapkan konsep NLP (Natural Language Processing) sederhana dalam konteks nyata.
**7. Tools & Library yang Digunakan**

- Python (Google Colab)
- pandas – untuk mengelola data
- nltk – untuk preprocessing teks
- scikit-learn – untuk CountVectorizer dan LatentDirichletAllocation

