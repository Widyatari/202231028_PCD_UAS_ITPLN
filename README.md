# PROJECT UAS AKHIR PEMOGRAMAN CITRA DIGITAL

Nama : Widya Tari
Nim 202231028

  #import cv2
  #import numpy as np
  #import matplotlib.pyplot as plt
Syntax ini digunakan untuk mengimpor (import) modul atau pustaka.
1. *import cv2* : Ini mengimpor modul cv2, yang merupakan pustaka OpenCV (Open Source Computer Vision Library). OpenCV adalah pustaka yang sangat populer untuk pemrosesan citra dan penglihatan komputer. Dengan mengimpor modul ini, Anda dapat menggunakan berbagai fungsi dan algoritma yang disediakan oleh OpenCV untuk manipulasi citra, deteksi objek, analisis video, dll.
2. *import numpy as np* : Ini mengimpor modul numpy dan mengalaminya dengan alias np. NumPy adalah pustaka fundamental dalam Python untuk komputasi numerik. Ini menyediakan struktur data yang kuat untuk bekerja dengan array dan matriks, serta berbagai fungsi matematika yang efisien. Dengan mengimpor NumPy, Anda dapat melakukan operasi matematika yang kompleks dan manipulasi data numerik dengan mudah.
3. *import matplotlib.pyplot as plt* : Ini mengimpor modul pyplot dari pustaka matplotlib dan mengalaminya dengan alias plt. Matplotlib adalah pustaka yang digunakan untuk visualisasi data dalam Python. Modul pyplot dari Matplotlib menyediakan fungsi untuk membuat plot dan grafik dengan cara yang mirip dengan MATLAB. Dengan mengimpor matplotlib.pyplot as plt, Anda dapat membuat grafik, plot, histogram, dan visualisasi data lainnya secara interaktif atau dalam skrip Python.

  #image_path = 'ProjectPCD.jpg'
Ini adalah sebuah statement yang mendefinisikan sebuah variabel image_path dan menginisialisasinya dengan nilai berupa string 'ProjectPCD.jpg'.
1. *Variabel* : image_path adalah nama variabel yang digunakan untuk menyimpan nilai berupa path atau lokasi dari sebuah file gambar (image file).
2. *Penugasan Nilai* : Tanda = digunakan untuk menugaskan nilai kepada variabel. Di sini, string 'ProjectPCD.jpg' ditugaskan ke variabel image_path.
3. *String* : 'ProjectPCD.jpg' adalah nilai yang ditugaskan ke variabel image_path. Ini adalah sebuah string yang merupakan nama file gambar beserta ekstensi file (jpg). Dalam konteks ini, string ini hanya berupa teks yang mengidentifikasi lokasi atau nama dari file gambar yang ingin dioperasikan di dalam kode Python.

  #image = cv2.imread(image_path)
Ini adalah sebuah statement yang menggunakan pustaka OpenCV (cv2) untuk membaca sebuah file gambar dari disk dan menyimpannya ke dalam variabel image.
1. *cv2.imread* : Ini adalah fungsi dari pustaka OpenCV (cv2) yang digunakan untuk membaca sebuah file gambar dari disk ke dalam bentuk array atau matriks yang dapat dikelola oleh Python. Fungsi ini mengambil satu parameter wajib yaitu image_path, yang merupakan string yang berisi path atau lokasi dari file gambar yang ingin dibaca.
2. *image_path* : Ini adalah variabel atau konstanta yang telah didefinisikan sebelumnya (seperti dalam contoh sebelumnya 'ProjectPCD.jpg') yang berisi path lengkap dari file gambar yang ingin dibaca.
3. *Penugasan Nilai* : Hasil dari pemanggilan cv2.imread(image_path) disimpan ke dalam variabel image. Variabel image akan berisi data citra yang telah dibaca, direpresentasikan sebagai array NumPy.

   #if image is None:
   #print("Gambar tidak ditemukan di jalur:", image_path)
      #else:
   #image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
   #gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 
   #edges = cv2.Canny(gray_image, 100, 200)
   #contours, _ = cv2.findContours(edges, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)  
   #image_contours = image_rgb.copy()
   #cv2.drawContours(image_contours, contours, -1, (0, 255, 0), 3)
Ini adalah blok kode yang mengandung beberapa langkah untuk memproses dan menganalisis gambar menggunakan pustaka OpenCV (cv2). Mari kita jelaskan setiap bagian dengan rinci:
1. *Pemeriksaan Ketersediaan Gambar* :
   if image is None :
       print("Gambar tidak ditemukan di jalur:", image_path)
  - if image is None : Ini adalah kondisi untuk memeriksa apakah variabel image yang sebelumnya dibaca dari cv2.imread(image_path) menghasilkan nilai None. Ini menunjukkan bahwa gambar tidak berhasil dibaca dari path yang diberikan.
  - print("Gambar tidak ditemukan di jalur :", image_path): Jika image bernilai None, maka cetak pesan yang menyatakan bahwa gambar tidak ditemukan di jalur yang ditentukan oleh image_path.
2. *Pemrosesan Gambar (Jika Gambar Tersedia)* :
   else:
       image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
       gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 
       edges = cv2.Canny(gray_image, 100, 200) 
       contours, _ = cv2.findContours(edges, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)  
       image_contours = image_rgb.copy()
       cv2.drawContours(image_contours, contours, -1, (0, 255, 0), 3)
   - image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB): Menggunakan cv2.cvtColor, gambar yang dibaca (image) dikonversi dari format warna BGR (default OpenCV) ke format RGB. Format RGB sering digunakan dalam banyak operasi visualisasi dan pemrosesan gambar di Python.
   - gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY): Menggunakan cv2.cvtColor, gambar asli (image) dikonversi ke citra skala abu-abu (grayscale). Citra skala abu-abu memungkinkan untuk analisis lebih lanjut seperti deteksi tepi atau segmentasi.
   - edges = cv2.Canny(gray_image, 100, 200): Menggunakan cv2.Canny, deteksi tepi Canny diterapkan pada citra skala abu-abu (gray_image). Parameter 100 dan 200 adalah ambang batas untuk deteksi tepi, yang dapat disesuaikan tergantung pada jenis gambar dan kebutuhan aplikasi.
   - contours, _ = cv2.findContours(edges, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE): Menggunakan cv2.findContours, kontur dari gambar yang telah diberi deteksi tepi ditemukan. Parameter edges adalah citra hasil dari deteksi tepi, cv2.RETR_TREE menunjukkan metode rekursif untuk penemuan kontur, dan cv2.CHAIN_APPROX_SIMPLE adalah metode pendekatan sederhana untuk merepresentasikan kontur.
   - image_contours = image_rgb.copy(): Membuat salinan gambar RGB (image_rgb) untuk tujuan menggambar kontur tanpa mempengaruhi gambar asli.
   - cv2.drawContours(image_contours, contours, -1, (0, 255, 0), 3): Menggambar kontur yang telah ditemukan (contours) pada gambar yang telah dikonversi ke RGB (image_contours). Warna kontur adalah (0, 255, 0) (hijau) dengan ketebalan garis 3 piksel.

  #plt.figure(figsize=(15, 10))
  #plt.subplot(2, 3, 1)
  #plt.imshow(image_rgb)
  #plt.title('Original Image')
  #plt.axis('off')

  #plt.subplot(2, 3, 2)
  #plt.imshow(edges, cmap='gray')
  #plt.title('Canny Edge Detection')
  #plt.axis('off')
  Ini adalah blok kode yang menggunakan pustaka matplotlib.pyplot (umumnya diakses sebagai plt) untuk membuat dan menampilkan dua subplot secara berurutan.
*Membuat Gambar Baru (Figure)* :
   plt.figure(figsize=(15, 10))
   - plt.figure(figsize=(15, 10)): Ini membuat sebuah gambar (figure) baru untuk menampung subplot-subplot yang akan ditambahkan. Parameter figsize=(15, 10) menentukan ukuran gambar dalam satuan inci (width, height). Dalam kasus ini, gambar memiliki ukuran 15 inci lebar dan 10 inci tinggi.

*Menambahkan Subplot Pertama*:
   python
   plt.subplot(2, 3, 1)
   plt.imshow(image_rgb)
   plt.title('Original Image')
   plt.axis('off')
   - plt.subplot(2, 3, 1): Ini menambahkan subplot pertama ke dalam gambar. Parameter pertama 2 menunjukkan bahwa gambar akan memiliki 2 baris subplot, parameter kedua 3 menunjukkan bahwa gambar akan memiliki 3 kolom subplot, dan parameter ketiga 1 menunjukkan bahwa subplot yang sedang ditambahkan adalah subplot pertama.
   - plt.imshow(image_rgb): Ini menampilkan gambar (image_rgb) pada subplot pertama yang telah ditentukan sebelumnya. image_rgb adalah variabel yang berisi gambar asli yang sudah dikonversi ke format RGB menggunakan OpenCV.
   - plt.title('Original Image'): Ini menambahkan judul 'Original Image' pada subplot pertama.
   - plt.axis('off'): Ini mengatur agar sumbu (axis) pada subplot pertama tidak ditampilkan.

*Menambahkan Subplot Kedua*:
   python
   plt.subplot(2, 3, 2)
   plt.imshow(edges, cmap='gray')
   plt.title('Canny Edge Detection')
   plt.axis('off')
   - plt.subplot(2, 3, 2): Ini menambahkan subplot kedua ke dalam gambar. Parameter pertama 2 menunjukkan bahwa gambar akan memiliki 2 baris subplot, parameter kedua 3 menunjukkan bahwa gambar akan memiliki 3 kolom subplot, dan parameter ketiga 2 menunjukkan bahwa subplot yang sedang ditambahkan adalah subplot kedua.
   - plt.imshow(edges, cmap='gray'): Ini menampilkan citra tepi (edges) pada subplot kedua yang telah ditentukan sebelumnya. edges adalah hasil dari deteksi tepi Canny yang telah diterapkan pada gambar dalam format skala abu-abu.
   - plt.title('Canny Edge Detection'): Ini menambahkan judul 'Canny Edge Detection' pada subplot kedua.
   - plt.axis('off'): Ini mengatur agar sumbu (axis) pada subplot kedua tidak ditampilkan.

