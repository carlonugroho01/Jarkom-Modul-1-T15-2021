# PRAKTIKUM 1 JARINGAN KOMUNIKASI - T15

Penyelesaian Soal Praktikum 1 Jaringan Komunikasi 2021\
Kelompok T15
  * Romandhika Rijal Ibrahim (05311840000048)
  * Muhammad Yasykur Rafii (05311940000017)
  * Stefanus Lionel Carlo Nugroho (05311940000027)

---

## Table of Contents

* [Soal 1](#soal-1)
* [Soal 2](#soal-2)
* [Soal 3](#soal-3)
* [Soal 4](#soal-4)
* [Soal 5](#soal-5)
* [Soal 6](#soal-6)
* [Soal 7](#soal-7)
* [Soal 8](#soal-8)
* [Soal 9](#soal-9)
* [Soal 10](#soal-10)
* [Soal 11](#soal-11)
* [Soal 12](#soal-12)
* [Soal 13](#soal-13)
* [Soal 14](#soal-14)
* [Soal 15](#soal-15)
* [Kendala](#kendala)

---
## Soal 1

### Deskripsi Soal
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 

### Pembahasan
1. Pertama-tama dalam menyelesaikan soal dilakukan filtering display dengan line filter `http.host contains "testing.mekanis.me"`
2. Muncul beberapa paket dan didapati pada paket paling bawah, pada bagian Hypertext Transfer Protocol `nginx/1.18.0 (Ubuntu)`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Screenshot%20(652).png">

Dapat disimpulkan bahwa webserver yang berkomunikasi menggunakan protokol HTTP didapati adalah nginx.

---
## Soal 2

### Deskripsi Soal
Temukan paket dari web-web yang menggunakan basic authentication method!

### Pembahasan 
1. Dalam menyelesaikan soal untuk menemukan paket-paket yang menggunakan basic authentication method dilakukan display filtering dengan line filter `http.authbasic`
2. Akan muncul paket-paket yang menggunakan basic authentication method

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%202.png">

Dapat disimpulkan bahwa paket-paket yang menggunakan basic authentication method adalah paket dengan nomor: 568, 573, dan 2066.

---
## Soal 3

### Deskripsi Soal
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

### Pembahasan 
1. Untuk mendapatkan username dan password dilakukan display filtering dari file 1-5.pcap dengan line filter `http.host=http.host==basic.ichimarumaru.tech`
2. Akan keluar beberapa packet, mencoba packet-packet yang memiliki keterangan method GET
3. Didapati pada bagian authorization sebagai berikut 'kuncimenujulautan:tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN'

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%203.png">

Dapat disimpulkan bahwa username: kuncimenujulautan dan password: tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN

4. Mengisi pertanyaan yang terdapat pada web yang sudah berhasil diakses

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%203(2).png">

---
## Soal 4

### Deskripsi Soal
Temukan paket mysql yang mengandung perintah query select!

### Pembahasan 
Untuk melakukan paket mysql yang mengandung perintah query select dilakukan dengan display filter `mysql contains SELECT || mysql contains select`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%204.png">

---
## Soal 5

### Deskripsi Soal
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

### Pembahasan 
Melakukan display filter `mysql contains INSERT || mysql contains insert`

<img width="500" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Screenshot%20(686).png">

---
## Soal 6

### Deskripsi Soal
Cari username dan password ketika melakukan login ke FTP Server!

### Pembahasan 
1. Untuk menemukan username dan password ketika melakukan login ke FTP server dari file 6-7.pcap, dilakukan display filter dengan line filter `ftp.request.command==USER||ftp.request.command==PASS`
2. Didapat paket-paket dengan info menjelaskan `Request: USER secretuser` dan `Request: PASS aku.pengen.pw.aja`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%206.png">

Dapat disimpulkan bahwa username: secretuser dan password: aku.pengen.pw.aja

---
## Soal 7

### Deskripsi Soal
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

### Pembahasan 
1. Untuk menemukan file pdf dari file-file zip yang ada dilakukan filtering displya dengan line filter `frame contains "Real.pdf`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%207.png">

2. Muncul 2 packet, dilakukan download dengan follow -> TCP Stream -> show data as RAW -> save as 201.zip
3. Buka zip yang sudah didownload dan didapati file real.pdf dalam zip tersebut, maka akan muncul gambar sebagai berikut

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%207%20(2).png">

---
## Soal 8

### Deskripsi Soal
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

### Pembahasan 
1. Untuk mencari paket yang menunjukkan pengambilan file dari FTP maka dilakukan display filter dari file 8-15.pcap dengan line filter `frame contains "RETR"`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%208.png">

Dapat disimpulkan bahwa tidak ada paket yang menunjukan pengambilan file dari FTP dari file 8-15.pcap

---
## Soal 9

### Deskripsi Soal
Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

### Pembahasan 
1. Untuk dapat menemukan file berisi data dengan nama "secret.zip" dari file 8-15.pcap dilakukan display filter dengan line filter `frame contains "secret.zip"`
2. Muncul Packet dengan info secret.zip, melakukan download file tersebut dengan melakukan klik kanan -> follow -> TCP Stream -> ASCII view -> save as secret.zip

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%209.png">

3. Membuka file secret.zip yang sudah didownload kemudian muncul kolom untuk memasukkan password sebagai berikut

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%209(2).png">

---
## Soal 10

### Deskripsi Soal
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

### Pembahasan 
1. Untuk dapat menemukan file dengan nama "history.txt" yang berisikan password untuk membuka file rahasia yang ada di "secret.zip" dilakukan display filter dengan line `frame contains"history.txt"`
2. Kemudian klik kanan -> follow -> TCP Stream dan muncul sebagai berikut

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2010.png">

Dapat diduga bahwa password dari file rahasia yang ada di "secret.zip" ada dalam file bukanapaapa.txt

3. Dilakukan display filter dengan line `ftp-data` kemudian mencari file yang berkaitan dengan bukanapaapa.txt

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2010%20(2).png">

Ditemukan pada bagian Line-based text data bahwa password adalah d1b1langbukanapaapajugagapercaya


4. Menggunakan password yang didapat untuk membuka file "wanted.pdf" yang terdapat dalam "secret.zip"

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2010%20(3).png">

---
## Soal 11

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

### Pembahasan 
1. Untuk menemukan paket-paket yang berasal dari port 80 maka dilakukan display filter pada halaman awal wireshark dengan line filter `src port 80`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2011.png">

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2011%20(2).png">

---
## Soal 12

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

### Pembahasan 
1. Untuk dapat mendapatkan paket yang mengandung port 21 maka dapat dilakukan display filter pada halaman awal wireshark dengan filter line `port 21` dengan pilihan localhost adapter for loopback traffic capture

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2012%20Rev.png">

2. Melakukan aktivasi xampp, menggunakan filezilla untuk mengkases port 21 dan melakukan transfer file untuk mentrigger packet diterima pada wireshark

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/File%20Nomor%2012%20(2).png">

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/File%20Nomor%2012%20(3).png">

3. Memeriksa apakah packet sudah ditangkap oleh wireshark

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/File%20Nomor%2012%20(4).png">


---
## Soal 13

### Deskripsi Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

### Pembahasan 
1. Untuk mendapat paket-paket yang tujuannya ke port 443, dibantu dengan membuka web monta.if.its.ac.id pada halaman incognito
2. Melakukan display filter pada halaman awal wireshark dengan line `dst port 443`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2013.png">

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2013%20(2).png">

---
## Soal 14

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

### Pembahasan 
1. Untuk mendapat paket-paket yang tujuannya ke kemenag.go.id dapat melakukan display filter pada halaman awal wireshark dengan line `dst host kemenag.go.id`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2014.png">

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2014%20(2).png">

---
## Soal 15

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### Pembahasan 
1. Untuk mendapat paket-paket yang tujuannya berasal dr ip sendiri, dapat melakukan pencarian ip address sendiri dahulu menggunakan command prompt, didapat IP address adalah 10.100.7.121
2. Melakukan display filter pada halaman awal wireshark dengan line `src host 10.100.7.121`

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2015.png">

<img width="900" alt="mkdir" src="https://github.com/carlonugroho01/Jarkom-Modul-1-T15-2021/blob/main/images/Soal%20Nomor%2015%20(2).png">

## Kendala
Tidak terdapat kendala yang berarti dalam pengerjaan dan revisi di praktikum Jaringan Komunikasi modul 1 ini
