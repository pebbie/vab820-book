# Video Capture

## ****gst-inspect****
+ Menampilkan daftar source plugin `gst-inspect | grep src`
+ Menampilkan daftar sink plugin `gst-inspect | grep sink`
+ Mencoba gstreamer `gst-launch videotestsrc ! glimagesink`
+ Menggunakan beberapa sink sekaligus menggunakan tee `gst-launch videotestsrc ! tee name=t t. ! queue ! glimagesink t. ! queue ! fakesink`

## plugin `tvsrc`
`tvsrc` akan menghasilkan data analog 720x576 (PAL) 30fps dengan tipe data `YUV420, fourcc(NV12)`

## plugin `glimagesink`
`glimagesink` tidak akan jalan kalau variabel `DISPLAY` tidak di-set sebelumnya (segmentation fault).

## plugin `ffmpegcolorspace`
plugin ini dapat digunakan untuk mentransformasi ruang warna dari data. 
Misalnya untuk kasus video analog, 

## plugin `appsink`