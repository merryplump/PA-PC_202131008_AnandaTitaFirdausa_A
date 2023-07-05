
# BACKGROUND REMOVAL

Background removal adalah proses mengisolasi objek utama dari latar belakang gambar dengan cara menghilangkan piksel-piksel latar belakang agar hanya objek yang tetap ada dalam gambar. Hal ini dilakukan dengan memanfaatkan perbedaan intensitas, warna, tekstur, atau fitur lainnya antara objek dan latar belakang.

### Kelebihan Background Removal
a. Segmentation: Background removal memungkinkan kita untuk memisahkan objek dari latar belakangnya dengan lebih akurat. Hal ini berguna dalam berbagai aplikasi seperti pengenalan objek, deteksi wajah, dan ekstraksi fitur.

b. Visualisasi: Dengan menghilangkan latar belakang, objek dapat ditampilkan secara lebih jelas dan fokus, sehingga memudahkan analisis dan interpretasi.

c. Kreativitas: Background removal membuka peluang untuk membuat komposisi gambar yang kreatif dengan menggabungkan objek dari berbagai latar belakang yang berbeda.

## Tahapan Pengerjaan Project
Pada potongan kode di atas, kita menggunakan beberapa library dan modul untuk memanipulasi gambar. Mari kita jelaskan langkah demi langkah:

1. Import library dan modul yang diperlukan:
   ```
   from IPython import display
   from rembg import remove
   from PIL import Image
   import cv2
   from skimage.io import imread
   import matplotlib.pyplot as plt
   %matplotlib inline
   ```
   - `IPython.display` digunakan untuk menampilkan gambar di notebook.
   - `rembg` adalah library yang digunakan untuk menghapus latar belakang gambar.
   - `PIL` adalah modul dari library Pillow untuk membaca, memanipulasi, dan menyimpan gambar.
   - `cv2` adalah modul dari library OpenCV untuk operasi pemrosesan gambar.
   - `skimage.io` digunakan untuk membaca gambar.

2. Mengimpor dan memproses gambar:
   ```
   citra1 = imread(fname='kucing.jpg')
   citra1 = cv2.cvtColor(citra1, cv2.COLOR_RGB2BGR)
   citra2  = imread(fname='BUKTI RINCIAN FOTO.jpg')
   citra2  = cv2.cvtColor(citra2, cv2.COLOR_RGB2BGR)
   ```
   - `imread` digunakan untuk membaca gambar dari file.
   - `cv2.cvtColor` digunakan untuk mengubah format warna gambar dari RGB menjadi BGR.

3. Menampilkan gambar menggunakan Matplotlib:
   ```
   fig, axes = plt.subplots(1,2, figsize=(10,10))
   ax = axes.ravel()

   ax[0].imshow(citra1)
   ax[0].set_title("Gambar Asli")
   ax[1].imshow(citra2)
   ax[1].set_title("Rincian Gambar")
   ```
   - `plt.subplots` digunakan untuk membuat grid gambar.
   - `ax.imshow` digunakan untuk menampilkan gambar pada setiap sumbu.
   - `ax.set_title` digunakan untuk memberikan judul pada setiap gambar.

4. Menyimpan gambar asli dalam format PNG:
   ```
   file_name = 'kucing.jpg'
   img = Image.open(file_name)
   img_name = 'Gambar_Asli'
   img.save('kucing3.png')
   ```
   - `Image.open` digunakan untuk membuka gambar menggunakan modul PIL.
   - `img.save` digunakan untuk menyimpan gambar dalam format PNG.

5. Menghapus latar belakang gambar menggunakan rembg:
   ```
   output_path = "kucing-removed-bg.png"

   with open(output_path, 'wb') as f:
       input_pict = open(file_name,'rb').read()
       subject = remove(input_pict) 
       f.write(subject)
   ```
   - `output_path` adalah path output file hasil penghapusan latar belakang.
   - `open(file_name, 'rb').read()` digunakan untuk membaca gambar sebagai binary.
   - `remove` digunakan untuk menghapus latar belakang gambar.
   - `f.write` digunakan untuk menulis hasil penghapusan latar belakang ke file output.

6. Menampilkan gambar hasil penghapusan latar belakang:
   ```
   display.Image(output_path)
   ```
   - `display.Image` digunakan untuk menampilkan gambar hasil penghapusan latar belakang.

   ## Jurnal Terkait

Link: https://e-jurnal.pelitanusantara.ac.id/index.php/mantik/article/view/265
 
#### Judul: 
IMPLEMENTASI TEKNIK THRESHODING PADA SEGMENTASI CITRA DIGITAL

#### Abstrak
AbstrakWarna yang diterima oleh mata dari sebuah objek ditentukan oleh warna sinar yang dipantulkan oleh objek tersebut. Digitalisasi  yaitu  gambar  yang  diolah  dengan  komputer  digital,  direpresentasikan  secara  numerik dengan nilai-nilai diskrit. Deteksitepimerupakan  langkah untuk  melengkapi informasi  di  dalam  citra, tepi mencirikan  batas-batas  objek  berguna  untuk  proses  segmentasi  dan  identifikasiobjek.Deteksi  tepi  citra bertujuan  meningkatkan  penampakangaris  batas  daerah  atau  objek. Proses  segmentasi  mengidentifikasi objek  dalam  beberapa  potongan  gambar  yang  bertujuan  untukmempermudah  membaca  informasi  citra.Metodesegmentasi mengasumsikan setiap  objek  cenderung  memiliki  warna  yang  homogen  dan  terletak pada  kisaran  keabuan  tertentu. Setiap  komponen  warna  menggunakan  8  bit  (nilainya  berkisar  antara  0 sampai  dengan  255). Proses thresholdingmengkonversi  citra  warna  menjadi  hitam  dan  putih  sehingga mempermudah mendeteksi objek.

#### Pendahuluan
Citra merupakan suatu representasi, kemiripan,    atau    imitasi    dari    suatu    objek,  sebagai  keluaran  suatu  sistem  perekaman  data dapat  bersifat optik  berupa  foto,  bersifat  analog berupa  sinyal-sinyal  video  seperti  gambar  pada monitor televisi, atau bersifat digital yang dapat langsung disimpan pada suatu media penyimpan.   Perbaikan   kualitas   citra (image enhancement)merupakan   salah   satu   proses dalam  pengolahan  citra (image  preprocessing).Perbaikan  kualitas  diperlukan  citra  diperlukan untuk  citra  mengalami  derau  (noise)  padasaat pengiriman   melalui   saluran   transmisi,   citra terlalu  terang/gelap,  citra  kurang  tajam,  kabur, dan sebagainya

#### Kesimpulan
Dari hasil penelitian dapat disimpulkan:

1.Teknik thresholdingmudah dilakukan dalam mengidentifikasi objek dengan memanfaatkan segmentasi citra yaitu memotong-motong bagian citra.

2.Identifikasi   citra   akan   valid   bila   proses segmentasi    dan    thresholding    pada    citra digital yang dominan warnanya. 

3.Deteksi  tepi  atau  deteksi  contur  dilakukan pada   bagian   citra   yang   dipotong-potonguntuk mempermudah deteksi tepi objek.

#### Referensi Jurnal
[1]Basuki,  Achmad  2005, Pengolahan Citra Digita  Menggunakan  Visual Basic, Graha Ilmu Jakarta.

[2]Destyningtias  B.,  Heranurweni  S.  dan T. Nurhayati.  2010.  Segmentasi  Citra  Dengan Metode   Pengambangan. Jurnal   Elektrika. Vol.2, No.1, 2010: 39 –49.

[3]Munir,   Rinaldi,   2004, Pengolahan Citra Digitaldengan    pendekatan    Algoritmik, Penerbit Informatika, Bandung.