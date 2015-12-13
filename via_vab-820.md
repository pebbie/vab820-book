# VIA VAB-820

VAB-820 merupakan komputer pico-ITX dari VIA yang menggunakan prosesor Freescale iMX6 Quad core.

Hal yang membuat saya memilih platform ini untuk pengembangan aplikasi computer vision antara lain : 
+ sudah ada port masukan untuk video analog (Composite/S-Video), termasuk chip untuk proses capture (ADV7180) sehingga tidak perlu lagi menggunakan perangkat terpisah (EasyCap)
+ sudah ada port CSI (Camera Serial Interface). Port yang sama yang digunakan oleh Raspberry Pi
+ Prosesor quad core untuk pilihan paralelisasi algoritma
+ Gigabit Ethernet. juga bisa dimanfaatkan untuk jalur video capture menggunakan converter analog to Ethernet