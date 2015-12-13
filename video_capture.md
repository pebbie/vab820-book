# Video Capture

## GStreamer 0.10

### ****gst-inspect****
+ Menampilkan daftar source plugin `gst-inspect | grep src`
+ Menampilkan daftar sink plugin `gst-inspect | grep sink`
+ Mencoba gstreamer `gst-launch videotestsrc ! glimagesink`
+ Menggunakan beberapa sink sekaligus menggunakan tee `gst-launch videotestsrc ! tee name=t t. ! queue ! glimagesink t. ! queue ! fakesink`

### plugin `tvsrc`
`tvsrc` akan menghasilkan data analog 720x576 (PAL) 30fps dengan tipe data `YUV420, fourcc(NV12)`

### plugin `glimagesink`
`glimagesink` tidak akan jalan kalau variabel `DISPLAY` tidak di-set sebelumnya (segmentation fault).

### plugin `ffmpegcolorspace`
plugin ini dapat digunakan untuk mentransformasi ruang warna dari data. 
Misalnya untuk kasus video analog, 

### plugin `appsink`

## OpenCV 2.4 

### integrasi dengan gstreamer
````
import gobject
gobject.threads_init()
import gst

pipeline = gst.Pipeline()
bin = gst.parse_bin_from_description('''
	tvsrc name=rca !
	appsink name=app emit-signals=True
	''', False)

def on_new_sample(sink):
    global img
    buffer = sink.emit('pull-buffer')
    if buffer:
	    height = 576
	    width = 720
        img_yuv = np.ndarray(shape=(height+height/2, width), \
dtype=np.uint8, buffer=buffer)
        img = cv2.cvtColor(img_yuv, cv2.COLOR_YUV2BGR_NV12)[:height,]
    return True

pipeline.add(bin)

appsink = pipeline.get_by_name("app")
appsink.connect('new-buffer', on_new_sample) 

pipeline.set_state(gst.STATE_PLAYING)

import cv2

while True:
    frame = img.copy()
    
    cv2.imshow("video", frame)

    k = cv2.waitKey(1)
    if k==27 or k==ord('q'): break

pipeline.set_state(gst.STATE_NULL)
cv2.destroyAllWindows()

```