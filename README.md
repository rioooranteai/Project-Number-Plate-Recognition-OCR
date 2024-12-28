# **Technical Report: Deteksi Plat Nomor Kendaraan Menggunakan OpenCV dan OCR**

---

## **1. Ringkasan**

Proyek ini bertujuan untuk mendeteksi dan mengenali plat nomor kendaraan dari gambar menggunakan kombinasi teknik *image processing* dan *Optical Character Recognition (OCR)*. Proses ini melibatkan beberapa tahap, termasuk *deskewing*, *denoising*, *binarization*, dan ekstraksi teks dengan **PaddleOCR** dan **EasyOCR**. Dataset yang digunakan berasal dari Kaggle untuk memastikan variasi gambar yang memadai. 

Hasil dari proyek ini diharapkan dapat membantu dalam otomatisasi proses identifikasi plat nomor untuk aplikasi seperti sistem parkir, pengawasan lalu lintas, dan penegakan hukum.

---

## **2. Motivasi**

Deteksi plat nomor kendaraan memiliki banyak aplikasi praktis, seperti:

- **Sistem Parkir Otomatis**: Mengidentifikasi kendaraan yang masuk dan keluar dari area parkir.
- **Pengawasan Lalu Lintas**: Mendeteksi pelanggaran lalu lintas.
- **Penegakan Hukum**: Membantu pihak berwenang melacak kendaraan terkait pelanggaran hukum.

Penggunaan teknik *image processing* dengan **OpenCV** dan *Optical Character Recognition (OCR)* memungkinkan proses identifikasi yang lebih cepat dan efisien dibandingkan metode manual.

---

## **3. Metrik Keberhasilan**

- **Akurasi Deteksi**: Seberapa tepat plat nomor berhasil dikenali dari gambar.
- **Kualitas OCR**: Evaluasi akurasi teks yang dihasilkan menggunakan Tesseract dan EasyOCR.
- **Waktu Pemrosesan**: Efisiensi dalam memproses dan mengenali plat nomor dari gambar.
- **Keberhasilan Deskewing dan Denoising**: Keberhasilan dalam mengoreksi kemiringan gambar dan mengurangi noise untuk meningkatkan akurasi OCR.

---

## **4. Kebutuhan & Batasan**

### **4.1 Kebutuhan Fungsional**

1. **Pengumpulan Dataset**: Mengambil dataset plat nomor kendaraan dari Kaggle.
2. **Preprocessing Data**:  
   - *Deskewing* gambar untuk mengoreksi kemiringan.  
   - *Denoising* untuk mengurangi noise dan mempertajam gambar.  
   - *Binarization* untuk mengubah gambar menjadi format hitam-putih.
3. **Deteksi Plat Nomor**: Menggunakan koordinat bounding box dari dataset untuk menandai area plat nomor.
4. **OCR**: Menggunakan **Tesseract**, **EasyOCR**, dan **PaddleOCR** untuk mengenali teks dari plat nomor.
5. **Ekspor Hasil**: Menyimpan hasil gambar dan anotasi dalam format ZIP.

### **4.2 Batasan**

- **Teknis**: Proses dilakukan secara offline menggunakan OpenCV dan OCR library.  
- **Dataset**: Terbatas pada dataset dari Kaggle `andrewmvd/car-plate-detection`.  
- **Waktu Pemrosesan**: Memerlukan waktu pemrosesan yang optimal agar dapat digunakan dalam aplikasi real-time.

### **4.3 Ruang Lingkup**

- **In-Scope**:  
  - Deteksi plat nomor dari gambar.  
  - Ekstraksi teks menggunakan Tesseract dan EasyOCR.  
  - Preprocessing gambar (deskewing, denoising, binarization).  

- **Out-of-Scope**:  
  - Implementasi real-time.  
  - Analisis performa untuk dataset yang lebih besar.  
  - Penggunaan model *deep learning* untuk deteksi plat nomor.

---

## **5. Metodologi**

### **5.1 Pernyataan Masalah**

Proyek ini memecahkan masalah deteksi dan pengenalan plat nomor kendaraan dari gambar statis menggunakan metode *image processing* dan OCR.

### **5.2 Data**

- **Sumber Data**: Dataset diambil dari Kaggle (`andrewmvd/car-plate-detection`).  
- **Format Data**:  
  - Gambar dalam format **PNG**.  
  - Anotasi dalam format **XML** yang berisi koordinat bounding box plat nomor.

### **5.3 Teknik yang Digunakan**

1. **Deskewing**  
   - Mengoreksi kemiringan gambar berdasarkan koordinat bounding box menggunakan **perspective transform** di OpenCV.

2. **Denoising**  
   - Mengurangi noise menggunakan metode **bilateral filter** dan mempertajam gambar dengan filter kernel.

3. **Binarization**  
   - Mengubah gambar menjadi hitam-putih menggunakan metode **thresholding**.

4. **OCR**  
   - **Tesseract**: Untuk mengenali teks dari gambar hasil binarization.  
   - **EasyOCR**: Alternatif OCR dengan dukungan untuk pengenalan karakter multi-bahasa.

5. **Ekspor Data**  
   - Menyimpan gambar dan anotasi ke dalam file ZIP untuk kebutuhan selanjutnya.

---

## **6. Kesimpulan**

Proyek ini berhasil mendeteksi dan mengenali plat nomor kendaraan dari gambar menggunakan metode *image processing* dengan OpenCV dan OCR. Teknik yang diterapkan membantu meningkatkan akurasi pengenalan teks dengan mengoreksi kemiringan gambar dan mengurangi noise.

---
