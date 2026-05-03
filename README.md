# 📸 Praktikum Pengolahan Citra - Segmentasi Citra

## 📌 Deskripsi
Proyek ini merupakan implementasi berbagai metode segmentasi citra menggunakan Python dan OpenCV. Tujuan dari praktikum ini adalah memahami cara memisahkan objek dari latar belakang berdasarkan intensitas piksel menggunakan beberapa teknik yang berbeda.

---

## ⚙️ Tools & Library
- Python
- OpenCV
- NumPy
- Matplotlib
- Scikit-image

---

## 🔄 Alur Praktikum

### 1. Pembuatan Citra Sintetis
Pada tahap awal dibuat citra grayscale berukuran 256x256 piksel yang berisi beberapa objek berbentuk lingkaran dengan intensitas berbeda. Ditambahkan noise agar menyerupai kondisi citra nyata, kemudian dilakukan Gaussian blur untuk menghaluskan citra.

---

## 🧪 Hasil Segmentasi

---

### 1️⃣ Thresholding
![Thresholding](https://github.com/apriliaputri2005-ops/CitraDigital_uts/blob/74af7fb2e9d51461902aa6ed82b48df019695d06/Thresholding.png)

**Penjelasan:**
Metode thresholding digunakan untuk memisahkan objek dari latar belakang berdasarkan nilai intensitas piksel.  
- Threshold global menggunakan nilai tetap  
- Otsu menentukan threshold secara otomatis  
- Adaptif menyesuaikan threshold di tiap area  

Hasil menunjukkan bahwa metode Otsu dan adaptif lebih optimal dibanding global.

---

### 2️⃣ Region Growing
![Region Growing](hasil/region_growing.png)

**Penjelasan:**
Region Growing dimulai dari seed point, kemudian memperluas area berdasarkan kemiripan intensitas piksel.  
Hasil segmentasi sangat dipengaruhi oleh:
- lokasi seed  
- nilai threshold  

Jika parameter tepat, objek dapat tersegmentasi dengan baik.

---

### 3️⃣ Deteksi Tepi
![Deteksi Tepi](hasil/deteksi_tepi.png)

**Penjelasan:**
Metode ini digunakan untuk mendeteksi batas objek.
- Sobel mendeteksi gradien horizontal & vertikal  
- Canny menghasilkan tepi lebih halus dan jelas  

Hasil menunjukkan bahwa Canny memberikan deteksi tepi terbaik.

---

### 4️⃣ K-Means Clustering
![K-Means](hasil/kmeans.png)

**Penjelasan:**
K-Means mengelompokkan piksel ke dalam beberapa cluster berdasarkan intensitas.  
Setiap piksel akan masuk ke cluster dengan centroid terdekat.

Hasil segmentasi menunjukkan pembagian citra menjadi beberapa bagian sesuai tingkat intensitas.

---

### 5️⃣ Watershed Segmentation
![Watershed](hasil/watershed.png)

**Penjelasan:**
Metode watershed digunakan untuk memisahkan objek yang saling berdekatan.  
Tahapan yang dilakukan:
1. Thresholding  
2. Morphological operation  
3. Distance transform  
4. Penentuan marker  
5. Proses watershed  

Hasil menunjukkan objek yang menempel dapat dipisahkan dengan baik.

---

## 📊 Kesimpulan

Setiap metode segmentasi memiliki kelebihan dan kekurangan masing-masing:
- Thresholding: sederhana namun terbatas  
- Region Growing: tergantung seed dan threshold  
- Deteksi tepi: hanya mendeteksi batas  
- K-Means: segmentasi berbasis clustering  
- Watershed: efektif untuk objek yang saling menempel  

Pemilihan metode harus disesuaikan dengan karakteristik citra.

---

## 📁 Struktur Folder
