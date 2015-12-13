# Yocto

Kompilasi pertama kali (menggunakan virtualbox) memakan waktu lama (sekitar 24 jam). 
Kompilasi selanjutnya lebih cepat karena memanfaatkan berkas-berkas yang sebelumnya pernah dibuat.

konfigurasi : `${BUILD_DIR}/conf/local.conf`

konfigurasi layer : `${BUILD_DIR}/conf/bblayers.conf`

lokasi resep : `sources/meta-*/*.bb`

resep image : `sources/meta-via-bsp/meta-vab-820/recipes-via/images/via-image-x11.bb`

lokasi paket yang sudah jadi : `${BUILD_DIR}/tmp/deploy/rpm`

lokasi image : `${BUILD_DIR}/tmp/deploy/images/imx6qvab820`

## Bitbake

perintah umum : `bitbake nama-resep`

kompilasi resep : `bitbake nama-resep -c package`

## Paket-paket esensial

### e2fsprogs
beberapa program penting yang ada di resep ini diantaranya: 
* `resize2fs`, digunakan untuk mengubah ukuran volume setelah partisinya diperbesar (menggunakan fdisk)
* `e2fsck`, digunakan untuk memperbaiki partisi jika terjadi hal.hal yang tidak diinginkan selama mengubah partisi
* 
e2fsprogs bawaan VIA masih berdasarkan distribusi Yocto Dora. 
Pada distribusi ini, paket e2fsprogs tidak mengandung resize2fs. Saya anjurkan mengganti resep ini dengan versi 1.42.9 dari distribusi terbaru Yocto. 