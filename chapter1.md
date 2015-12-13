# Desktop

VAB-820 menggunakan Matchbox WM sebagai Aplikasi Window Manager.

Daftar kategori aplikasi ada di `/usr/share/matchbox/vfolders`.

Daftar aplikasi ada di `/usr/share/applications/*.desktop`.

Lokasi log ada di `/var/log/XSession`.

## Pengubahan entri desktop

Perubahan pasca penyuntingan berkas `*.desktop` di direktori `/usr/share/applications` hanya akan dilakukan jika ada berkas yang dihapus/ditambah. 
Oleh sebab itu, untuk mengubah konfigurasi pada entri berkas `.desktop` sebaiknya dilakukan di direktori lain. 
Sebelum dilakukan penyuntingan, pindahkan berkas yang mau diubah ke direktori lain (misal, `~/Desktop`).
Setelah selesai dilakukan penyuntingan, Pindahkan kembali ke lokasi semula. 