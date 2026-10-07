# face_filter — BINUS@Medan Photobooth

Filter wajah berbasis kamera (kacamata, heart eyes, topi, gesture, BINUS@Medan) yang berjalan di browser.

## Cara menjalankan

1. Buka `index.html` di **Google Chrome** atau **Microsoft Edge** (klik dua kali file-nya, atau buka lewat web server lokal).
2. Izinkan akses kamera.
3. Tekan **F11** untuk fullscreen.
4. Pertama kali saja: klik **FOLDER: PILIH**, lalu pilih folder untuk menyimpan foto. Folder ini akan diingat.

Model AI (MediaPipe) dimuat dari internet saat halaman dibuka, jadi butuh koneksi internet ketika start.

## Alur foto

1. Pilih filter dengan gesture atau keyboard (`1` kacamata, `2` heart eyes, `3` topi, `←`/`→` ganti style, `B` BINUS, `X` matikan semua).
2. Klik **[ FOTO ]**, tekan `V`, atau tahan gesture peace ✌. Muncul countdown 3-2-1, lalu **satu** foto diambil.
3. Preview foto muncul dengan form **Nama Lengkap** dan **No HP**. Kedua kolom wajib diisi:
   - No HP hanya angka, diawali `08` (9–13 digit) atau `628` (10–14 digit).
4. Klik **SIMPAN** untuk menyimpan foto, atau **BATAL**/`ESC` untuk membuang foto.

Nama file dibuat dari nama lengkap dan No HP:

```
Jessi Tan, 08121231231  ->  foto-jessi-tan-08121231231.jpg
```

Kalau nama file itu sudah ada, file baru menjadi `foto-jessi-tan-08121231231-2.jpg`, lalu `-3`, dan seterusnya. Foto lama tidak pernah ditimpa.

Foto disimpan dalam resolusi asli kamera, JPEG kualitas 95, dengan mirror yang sama seperti preview dan semua filter yang sedang aktif. Skeleton tangan dan lingkaran progress gesture tidak ikut masuk ke foto.

Browser yang tidak mendukung pemilihan folder akan menyimpan foto ke folder **Downloads**.

## Troubleshooting

- **CAMERA_ERROR**: tutup aplikasi lain yang memakai kamera (Zoom, Teams, Camera), izinkan kamera di browser, lalu refresh.
- **VISION_ERROR**: model AI gagal dimuat. Periksa koneksi internet, lalu refresh.
- Angka FPS dan waktu AI per inference (`AI xx ms`) ditampilkan di baris STATE.
