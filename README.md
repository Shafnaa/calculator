# Tugas Besar Sistem Mikroprosessor
Merancang kalkulator menggunakan mikroprosessor AT80S52, keypad, LCD 16x2, dan bahasa assembly.

Pada project ini, bahasa Assembly digunakan untuk membuat kalkulator sederhana menggunakan keypad sebagai input dan LCD display sebagai output.

Dalam perancangan kalkulator ini, menggunakan Proteus untuk melakukan simulasi dan merancang PCB. Kemudian melakukan uji pada breadboard dengan menggunakan Arduino sebagai uploader.

![image](https://github.com/Shafnaa/calculator/assets/88240429/04e445cd-7f03-4236-96a9-85055ce724aa)

## Spesifikasi

Dikarenakan hampir setiap register pada 8052 itu 8-bit, kalkulator ini hanya bekerja dalam rentang 0-255. Fitur:

- Penjumlahan,
- Pengurangan,
- Perkalian,
- Pembagian,
- Reset mikroprosessor dan LCD saat 'ON/CE' ditekan.

LCD akan menampilkan pesan error "OVERFLOW!" jika input atau outputnya melebihi rentang 0-255, maka dari itu angka negatif juga tidak dapat dijalankan.
Akan menampilkan pesan error lain "DIV BY 0" jika pengguna mencoba membagi dengan nol.
Keterbatasan lain adalah kalkulator ini hanya dapat bekerja dengan 2 bilangan. Jadi, misal mencoba memasukan "1+2+3", saat "=" ditekan, ia hanya akan melakukan "1+3" karena program hanya akan menyimpan angka pertama dan terakhir.

### Link Tutorial Arduino Sebagai Uploader

https://youtu.be/8255_CHE5gE?si=fZOEaZyGLwA6_3DN

Download file "AVR8051.conf" terlebih dahulu kemudian ikuti langkah pada video. 

Command yang digunakan sebagai berikut:

"C:\Program Files (x86)\Arduino\hardware\tools\avr\bin\avrdude.exe" -C C:/AVR8051.conf -c stk500v1 -P COM5 -p 89s52/1 -b 19200 -U flash:w:"PATH":a
