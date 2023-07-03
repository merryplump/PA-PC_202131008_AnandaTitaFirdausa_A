
# BACKGROUND REMOVAL

Background removal adalah proses mengisolasi objek utama dari latar belakang gambar dengan cara menghilangkan piksel-piksel latar belakang agar hanya objek yang tetap ada dalam gambar. Hal ini dilakukan dengan memanfaatkan perbedaan intensitas, warna, tekstur, atau fitur lainnya antara objek dan latar belakang.

#### Kelebihan Background Removal
a. Segmentation: Background removal memungkinkan kita untuk memisahkan objek dari latar belakangnya dengan lebih akurat. Hal ini berguna dalam berbagai aplikasi seperti pengenalan objek, deteksi wajah, dan ekstraksi fitur.

b. Visualisasi: Dengan menghilangkan latar belakang, objek dapat ditampilkan secara lebih jelas dan fokus, sehingga memudahkan analisis dan interpretasi.

c. Kreativitas: Background removal membuka peluang untuk membuat komposisi gambar yang kreatif dengan menggabungkan objek dari berbagai latar belakang yang berbeda.

## Tahapan Project

Source code yang dilampirkan menggunakan library "rembg" untuk menghapus latar belakang (background) gambar. Berikut adalah penjelasan langkah-langkahnya:

1. `pip install rembg --user`: Perintah ini untuk menginstal pustaka "rembg" menggunakan pip, yang merupakan manajer paket Python. "--user" digunakan untuk menginstal pustaka secara lokal untuk pengguna saat ini.

2. `from rembg import remove`: Baris ini mengimpor fungsi "remove" dari modul "rembg". Fungsi ini akan digunakan untuk menghapus latar belakang gambar.

3. `from PIL import Image`: Baris ini mengimpor kelas "Image" dari modul "PIL". Modul "PIL" (Python Imaging Library) digunakan untuk memanipulasi gambar.

4. `input_path = 'kucing.jpg'`: Variabel "input_path" berisi path atau lokasi file gambar input yang ingin dihapus latar belakangnya. Dalam contoh ini, file gambar inputnya adalah "kucing.jpg".

5. `output_path = 'kucing-removedbg.png'`: Variabel "output_path" berisi path atau lokasi file gambar hasil yang akan disimpan setelah latar belakangnya dihapus. Dalam contoh ini, file gambar hasil akan disimpan dengan nama "kucing-removedbg.png".

6. `input = Image.open(input_path)`: Baris ini membuka file gambar input menggunakan metode "open" dari kelas "Image" dalam modul "PIL". Gambar input akan dijadikan objek "input" yang akan digunakan sebagai parameter pada fungsi "remove".

7. `output = remove(input)`: Baris ini memanggil fungsi "remove" dari pustaka "rembg" dengan memberikan objek gambar "input" sebagai parameter. Fungsi "remove" akan menghapus latar belakang gambar dan mengembalikan gambar hasil dalam bentuk objek.

8. `output.save(output_path)`: Baris ini menyimpan gambar hasil yang telah memiliki latar belakang dihapus ke file dengan path atau lokasi yang ditentukan dalam variabel "output_path". Metode "save" digunakan untuk menyimpan objek gambar "output" ke dalam file gambar dengan format PNG.

## Jurnal Terkait
1. https://e-jurnal.pelitanusantara.ac.id/index.php/mantik/article/view/265

2. https://journal.uii.ac.id/Snati/article/view/3000

3. http://download.garuda.kemdikbud.go.id/article.php?article=2928867&val=25864&title=Penerapan%20Metode%20Background%20Subtraction%20Untuk%20Deteksi%20Gerak%20Pada%20Kendaraan