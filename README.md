# SIG_TEORI_TGS12
 georeferencing aerial imagery
 
 # Langkah Kerja :

1. Kami akan menggunakan peta dasar dari OpenStreetMap untuk menangkap koordinat untuk georeferensi. QGIS3 hadir dengan dukungan bawaan untuk lapisan ubin. Ini umumnya dikenal sebagai lapisan 'XYZ' karena dibuat menggunakan ubin peta individual untuk setiap tingkat zoom (z) pada kisi koordinat x,y. Anda dapat menemukan lapisan OpenStreetMap di bawah XYZ Tiles di Panel Browser. Seret layer ke kanvas utama. Setelah dimuat, catat Coordinate Reference System (CRS) untuk lapisan ini di bagian kanan bawah corder. Ini ditetapkan sebagai EPSG 3857 Pseudo Mercator. Ini penting karena koordinat yang kita simpulkan dari lapisan ini selama georeferensi akan berada di CRS ini.

2. Gambar yang kami georeferensi adalah untuk Washington Square Park, New York. Anda dapat memperbesar/menggeser untuk menemukan taman ini di peta. Tapi itu rumit dan tidak praktis. Dari QGIS versi 3.20 dan seterusnya, ada dukungan bawaan untuk Nominatim Geocoder berbasis OpenStreetMap. Klik bilah pencarian di kiri bawah jendela QGIS. Untuk menggunakan ini sebagai awalan geocoder, tempat pencarian dengan >. Mencari > Washington Square Park akan memunculkan daftar alamat untuk dipilih. Klik alamat pertama.

3. Kanvas peta akan dipusatkan ke Square Park. Sekarang mari kita mulai Georeferencer. Luncurkan Georeferensi dari Raster ‣ Georeferencer.

4. Untuk georeferensi gambar udara, kita harus memilih titik koordinat dari OpenStreetMap, jadi pertama-tama mari kita masukkan alat Georeferencer ke jendela utama QGIS. Pilih Konfigurasikan Georeferensi dari Settings ‣ Configure Georeferencer.

5. Centang Show georeferencer window docked dan klik OK.

6. Jendela Georeferencer akan diletakkan di bagian bawah jendela utama QGIS. Mari memuat file gambar dengan mengklik ikon Open Raster di jendela Georeferencer dan menavigasi ke file JPG yang diunduh. Klik Open.

7. Sebelum menambahkan Ground Control Points (GCP), kita perlu mendefinisikan Transformation Settings. Klik pada ikon Transformation Settings untuk membuka dialog Transformation Settings. Pilih jenis Transformation sebagai Polinomial 2. Lihat Dokumentasi QGIS untuk mempelajari tentang berbagai jenis transformasi dan kegunaannya. Seperti disebutkan sebelumnya, peta dasar kami ada di EPSG 3857 Pseudo Mercator CRS, jadi tetapkan itu sebagai Target CRS. Anda dapat membiarkan nama raster Output ke default dan memilih LZW sebagai Compression. Centang Gunakan 0 untuk transparansi bila diperlukan. Centang Simpan poin GCP untuk menyimpan poin sebagai file terpisah untuk keperluan di masa mendatang. Pastikan opsi Muat di QGIS saat selesai dicentang. Klik OK.

8. Sekarang klik tombol Add Point pada toolbar dan pilih lokasi yang mudah diidentifikasi pada gambar. Sudut, persimpangan, tiang dll, membuat titik kontrol yang baik. Setelah Anda mengklik gambar di lokasi titik kontrol, Anda akan melihat pop-up yang meminta Anda untuk memasukkan koordinat peta. Klik tombol Dari kanvas peta.

9. Di lapisan OpenStreetMap, klik lokasi yang tepat di lapisan referensi. Koordinat akan diisi secara otomatis dari klik Anda pada kanvas peta. Klik Ok.

10. Demikian pula, pilih setidaknya 6 titik pada gambar dan tambahkan koordinatnya dari lapisan referensi. Setelah Anda menambahkan jumlah poin minimum yang diperlukan untuk transformasi, Anda akan melihat bahwa GCP sekarang memiliki nilai kesalahan dX, dY, dan Residual bukan nol. Jika GCP tertentu memiliki nilai error yang luar biasa tinggi, hal itu biasanya berarti kesalahan manusia dalam memasukkan nilai koordinat. Jadi, Anda dapat menghapus GCP itu dan menangkapnya lagi.

11. Setelah Anda puas dengan GCP, klik Mulai georeferensi. Ini akan memulai proses melengkungkan gambar menggunakan GCP dan membuat raster target. Setelah proses selesai, Anda akan melihat layer dimuat di QGIS. Tutup jendela Georeferencer.

12. Sekarang klik pada ikon Open layer styling panel dan Switch to the Transparency tab. Tambahkan 255 sebagai nilai tambahan tanpa data. Ini akan menghapus batas putih di sekitar gambar. Sekarang Anda akan melihat gambar georeferensi Anda dilapis dengan baik pada lapisan dasar.
 
