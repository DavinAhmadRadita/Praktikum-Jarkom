# Modul 4

## 4.2 NsLookup
nslookup adalah sebuah perintah atau alat yang digunakan untuk mencari dan menampilkan informasi DNS, seperti mengetahui alamat IP dari suatu nama domain atau sebaliknya, sehingga sering dipakai untuk mengecek dan menganalisis koneksi jaringan.

## Langkah - Langkah
1. Buka cmd lalu ketik "nslookup www.mit.edu" lalu enter, command tersebut untuk melihat IP domain
<img width="452" height="295" alt="image" src="https://github.com/user-attachments/assets/d019669b-1289-43ad-b599-1c1b8d83bc62" />

2. ketik "nslookup –type=NS mit.edu" pada cmd lalu enter, command tersebut untuk menampilkan daftar name server yang terhubung
<img width="716" height="546" alt="image" src="https://github.com/user-attachments/assets/9b01e3a2-d43e-411c-8134-caacbef249f1" />

3. ketik "nslookup www.aiit.or.kr bitsy.mit.edu" pada cmd lalu enter, command tersebut untuk meminta informasi tentang IP address dari domain www.aiit.or.kr ke server DNS bitsy.mit.edu
<img width="645" height="372" alt="image" src="https://github.com/user-attachments/assets/8ffbac68-3cf9-471c-b81d-7b9e7f56de2b" />

# Pertanyaan
**1. Jalankan nslookup untuk mendapatkan alamat IP dari server web di Asia. Berapa alamat IP server tersebut?**

IP yang di dapat dari web www.nus.edu.sg adalah 45.60.35.225
<img width="479" height="232" alt="image" src="https://github.com/user-attachments/assets/05892cec-b1d1-4623-bd0a-1deb65fd18b0" />

**2. Jalankan nslookup agar dapat mengetahui server DNS otoritatif untuk universitas di Eropa.**

salah satu kampus yang saya pakai untuk mengetahui server DNS adalah Technical University Of Munich, Untuk mencari nya menggunakan command "nslookup -type=ns tum.de"
<img width="828" height="363" alt="image" src="https://github.com/user-attachments/assets/717635f1-907e-43e7-9a95-6868c258e82a" />

**3. Jalankan nslookup untuk mencari tahu informasi mengenai server email dari Yahoo! Mail melalui salah satu server yang didapatkan di pertanyaan nomor 2. Apa alamat IP-nya ?**

Saya menggunakan server DNS dari domain tum.de, yaitu

- dns1.lrz.de

- dns2.lrz.bayern

- dns3.lrz.eu 

Ketika dilakukan perintah nslookup untuk mencari server email (MX) dari yahoo.com menggunakan salah satu DNS tersebut, hasil yang diperoleh adalah “Query refused”. Hal ini terjadi karena server DNS tersebut tidak mengizinkan permintaan query dari luar jaringan mereka (bersifat terbatas/internal), sehingga alamat IP server email Yahoo Mail tidak dapat diketahui melalui DNS tersebut.

<img width="707" height="421" alt="image" src="https://github.com/user-attachments/assets/65c30259-a912-4b40-b503-3d5dfcc89444" />

## 4.3 IP Config

IP Config adalah sebuah perintah yang digunakan untuk menampilkan informasi konfigurasi jaringan pada komputer, seperti alamat IP, subnet mask, dan default gateway.

## Langkah - Langkah
1. Buka cmd lalu ketik "ipconfig /all" lalu enter, command tersebut untuk menampilkan IP dan DNS pada laptop
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a576f5b8-e32c-40c4-8519-d21a7dbf9b97" />

2. Ketik "ipconfig /all > networkinfo.txt" pada cmd lalu enter, command tersebut untuk menyimpan IP dan DNS yang sudah di tampilkan namun di simpan berupa file txt.
<img width="588" height="72" alt="image" src="https://github.com/user-attachments/assets/86c288da-e800-44f7-857f-8b9a67e63dd0" />

Contoh file 

<img width="757" height="33" alt="image" src="https://github.com/user-attachments/assets/ed4f6855-8632-4468-996a-dbabf941d881" />

3. Ketik "ipconfig /displaydns" pada cmd lalu enter, command tersebut untuk menampilkan DNS
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/480b0764-4e69-4d18-ab07-97c8da0934af" />

4. Ketik "ipconfig /flushdns" pada cmd lalu enter, command tersebut untuk menghapus DNS yang di telah buka pada device
<img width="552" height="130" alt="image" src="https://github.com/user-attachments/assets/dc5faa8c-b005-43d5-a8c3-b42d40f40c62" />

## 4.3 Tracking DNS dengan WireShark
