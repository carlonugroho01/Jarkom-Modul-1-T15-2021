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

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Dapat disimpulkan bahwa paket-paket yang menggunakan basic authentication method adalah paket dengan nomor: 568, 573, dan 2066.

---
## Soal 3

### Deskripsi Soal
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

### Pembahasan 
1. Untuk mendapatkan username dan password dilakukan display filtering dari file 1-5.pcap dengan line filter `http.host=http.host==basic.ichimarumaru.tech`
2. Akan keluar beberapa packet, mencoba packet-packet yang memiliki keterangan method GET
3. Didapati pada bagian authorization sebagai berikut 'kuncimenujulautan:tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN'

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Dapat disimpulkan bahwa username: kuncimenujulautan dan password: tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN

---
## Soal 4

### Deskripsi Soal
Temukan paket mysql yang mengandung perintah query select!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 5

### Deskripsi Soal
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 6

### Deskripsi Soal
Cari username dan password ketika melakukan login ke FTP Server!

### Pembahasan 
1. Untuk menemukan username dan password ketika melakukan login ke FTP server dari file 6-7.pcap, dilakukan display filter dengan line filter `ftp.request.command==USER||ftp.request.command==PASS`
2. Didapat paket-paket dengan info menjelaskan `Request: USER secretuser` dan `Request: PASS aku.pengen.pw.aja`

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Dapat disimpulkan bahwa username: secretuser dan password: aku.pengen.pw.aja

---
## Soal 7

### Deskripsi Soal
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

### Pembahasan 
1. Untuk menemukan file pdf dari file-file zip yang ada dilakukan filtering displya dengan line filter `frame contains "Real.pdf`
2. Muncul 2 packet, dilakukan download dengan follow -> TCP Stream -> show data as RAW -> save as 201.zip
3. Buka zip yang sudah didownload dan didapati file real.pdf dalam zip tersebut, maka akan muncul gambar sebagai berikut

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

---
## Soal 8

### Deskripsi Soal
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 9

### Deskripsi Soal
Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 10

### Deskripsi Soal
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 11

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 12

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 13

### Deskripsi Soal
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 14

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

---
## Soal 15

### Deskripsi Soal
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### Pembahasan 
Lorem Ipsum lorem ipsum

<img width="500" alt="mkdir" src="https://user-images.githubusercontent.com/57980125/121776710-9b9b4f80-cbb8-11eb-8997-4276a9a2263d.png">

Kemudian dilakukan pemetaan tiap-tiap karakter sebagai hasil dari enkripsi dengan loop.

## Kendala
- Soal 1 : Belum berhasil membuat log khusus untuk enkripsi-dekripsi AtoZ
- Soal 2 : Belum berhasil membuat fungsi vigenere ketika dilakukan rename serta membagi file ke dalam file-file kecil berukuran 1024mb
- Soal 3 : Belum dapat memahamai soal
- Soal 4 : -
