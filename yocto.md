# Yocto

konfigurasi : `${BUILD_DIR}/conf/local.conf`

konfigurasi layer : `${BUILD_DIR}/conf/bblayers.conf`

lokasi resep : `sources/meta-*/*.bb`

resep image : `sources/`

lokasi paket yang sudah jadi : `${BUILD_DIR}/tmp/deploy/rpm`

lokasi image : `${BUILD_DIR}/tmp/deploy/images`

## Bitbake

`bitbake nama-resep`

kompilasi resep : `bitbake nama-resep -c package`