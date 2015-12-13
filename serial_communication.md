# Serial Communication

VAB-820 punya dua port serial :
* /dev/ttymxc0
  
Lokasi port ini ada di sisi yang sama dengan batere RTC. 
Port ini dapat digunakan untuk komunikasi dengan device lain.

* /dev/ttymxc1
    
Lokasi port ini ada di sisi yang sama dengan port Power Supply.
Port ini digunakan sebagai jalur DEBUG. 
Ketika terhubung, sistem akan mengaktifkan getty di port tersebut. 
Baud rate yang digunakan adalah 115200
    
