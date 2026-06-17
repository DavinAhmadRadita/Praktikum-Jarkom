# MODUL 10 IP

IP (Internet Protocol) adalah alamat unik yang dimiliki setiap perangkat yang terhubung ke jaringan komputer atau internet. Alamat IP berfungsi sebagai identitas perangkat sehingga data dapat dikirim dan diterima dengan tepat antara satu perangkat dengan perangkat lainnya. Dalam komunikasi jaringan, IP digunakan untuk menentukan sumber dan tujuan pengiriman data. Contohnya, ketika sebuah komputer mengakses website atau terhubung ke server chat, alamat IP digunakan untuk menemukan perangkat tujuan agar komunikasi dapat berlangsung dengan benar.

## Langkah-Langkah

1. Buka CMD lalu ketik ipconfig pada cdm untuk melihat ip dari perangkat yang digunakan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e7e031c7-9dbb-45a2-ba02-bfcc5aedf61b" />

Perangkat menggunakan alamat IP 192.168.0.102 yang termasuk dalam jaringan private class c. Subnet mask 255.255.255.0 digunakan untuk memisahkan bagian network dan host pada jaringan.

# TRACEROUTE

Traceroute adalah utilitas jaringan yang digunakan untuk melacak jalur atau rute yang dilalui paket data dari komputer sumber menuju komputer tujuan di jaringan atau internet. Traceroute bekerja dengan menampilkan setiap perangkat perantara (router) yang dilewati paket beserta waktu yang dibutuhkan untuk mencapai perangkat tersebut. Dengan menggunakan traceroute, pengguna dapat mengetahui jalur komunikasi data, mengidentifikasi titik terjadinya keterlambatan, serta membantu proses analisis dan pemecahan masalah pada jaringan komputer.

## Langkah-Langkah

1. Buka CMD, lalu ketik tracert google.com
<img width="857" height="425" alt="image" src="https://github.com/user-attachments/assets/085b01ab-49e2-4368-b25d-b5e33f0b27e9" />

Paket data mencapai server Google dalam 11 hop. Hop pertama (192.168.0.1) merupakan router lokal atau default gateway yang digunakan perangkat untuk terhubung ke jaringan. Hop kedua hingga keenam (192.168.1.1, 10.194.0.1, 172.16.33.149, 172.17.2.54, dan 172.17.2.69) masih berada pada jaringan internal milik ISP, yang terlihat dari penggunaan alamat IP privat. Pada hop ketujuh terjadi Request Timed Out, yang menunjukkan router tersebut tidak memberikan respons terhadap permintaan traceroute. Setelah itu, paket memasuki jaringan publik internet melalui beberapa router dengan alamat IP publik pada hop kedelapan hingga kesepuluh (142.250.175.134, 209.85.255.97, dan 74.125.251.205). Akhirnya, pada hop ke-11 paket berhasil mencapai server Google dengan alamat 216.239.38.120 (any-in-2678.1e100.net) dengan waktu tempuh rata-rata sekitar 26 ms.

