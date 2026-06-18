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

# IMCP, MTU, TTL

**ICMP (Internet Control Message Protocol)** adalah protokol jaringan yang digunakan untuk mengirimkan pesan kontrol dan informasi kesalahan antar perangkat dalam jaringan. ICMP membantu proses diagnosis dan pemantauan jaringan, misalnya pada perintah ping untuk menguji konektivitas dan traceroute untuk melacak jalur paket data menuju tujuan.

**MTU (Maximum Transmission Unit)** adalah ukuran maksimum paket data yang dapat dikirim melalui suatu jaringan dalam satu kali transmisi tanpa harus dipecah (fragmentasi). Nilai MTU yang umum digunakan pada jaringan Ethernet adalah 1500 byte. Jika ukuran data melebihi MTU, paket akan dipecah menjadi beberapa bagian agar dapat dikirim melalui jaringan.

**TTL (Time To Live)** adalah nilai yang menentukan berapa banyak router atau hop yang dapat dilewati oleh sebuah paket data sebelum paket tersebut dibuang. Setiap kali paket melewati router, nilai TTL akan berkurang satu. Jika TTL mencapai nol, paket akan dihentikan dan router akan mengirimkan pesan ICMP kembali ke pengirim. Mekanisme ini mencegah paket beredar terus-menerus dalam jaringan akibat kesalahan routing.

# FRAGMENTASI

Fragmentasi adalah proses pemecahan sebuah paket data menjadi beberapa paket yang lebih kecil karena ukuran paket tersebut melebihi nilai MTU (Maximum Transmission Unit) pada jaringan yang dilaluinya. Setiap fragmen akan dikirim secara terpisah melalui jaringan dan kemudian disusun kembali menjadi paket utuh ketika mencapai tujuan. Fragmentasi memungkinkan data tetap dapat dikirim meskipun terdapat perbedaan kapasitas MTU antar jaringan, tetapi terlalu banyak fragmentasi dapat menurunkan kinerja jaringan karena menambah waktu pemrosesan dan meningkatkan kemungkinan kehilangan paket.

## Langkah-Langkah

1. Open wireshark lalu pilih interface wifi yang aktif
2. lalu click start
3. buka CMD lalu ketik ping google.com -l 2000
<img width="752" height="258" alt="image" src="https://github.com/user-attachments/assets/750f7bb9-629c-4844-9cc5-6ba390cee91b" />

4. lalu kembali ke wireshark dan ketik "ip.flags.mf == 1 || ip.frag_offset > 0" pada search bar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b5169e19-7d31-4c0c-9326-9106e72ac158" />

• Berdasarkan hasil capture Wireshark pada jaringan, terlihat beberapa paket ICMP mengalami proses fragmentasi. Hal ini ditunjukkan oleh informasi "Fragmented IP protocol (proto=ICMP 1)" pada paket IPv4 yang dikirim dari alamat IP 10.144.53.204 menuju 172.253.118.113.

• Ukuran paket yang tercatat sebesar 1514 bytes, sehingga melebihi batas MTU standar Ethernet sekitar 1500 bytes dan menyebabkan paket harus dipecah menjadi beberapa fragmen. Pada detail paket juga terdapat nilai ID=fb61, ID=fb62, ID=fb63, dan ID=fb64 yang menunjukkan bahwa fragment-fragment tersebut berasal dari paket data yang sama.

• Nilai off=0 menandakan fragmen pertama dari paket yang dikirim. Selain itu, ditemukan keterangan "Reassembled in #3693", "#3940", "#4150", dan "#4347" yang menunjukkan bahwa seluruh fragmen berhasil digabung kembali menjadi paket ICMP utuh oleh perangkat tujuan. Paket ICMP tersebut berupa Echo (ping) request dengan nilai TTL sebesar 128.

Dari hasil analisis tersebut dapat disimpulkan bahwa paket ping yang dikirim mengalami fragmentasi karena ukuran data melebihi kapasitas MTU jaringan yang digunakan, namun seluruh fragmen berhasil direassembly sehingga paket dapat diterima dengan baik oleh tujuan.


# IPv6

IPv6 (Internet Protocol Version 6) adalah versi terbaru dari protokol IP yang digunakan untuk mengidentifikasi dan menghubungkan perangkat dalam jaringan komputer maupun internet. IPv6 dikembangkan sebagai pengganti IPv4 karena jumlah alamat IPv4 yang tersedia semakin terbatas. Dengan panjang alamat 128 bit, IPv6 mampu menyediakan jumlah alamat yang sangat besar sehingga dapat mendukung pertumbuhan perangkat yang terhubung ke internet. Selain itu, IPv6 menawarkan efisiensi routing yang lebih baik, konfigurasi alamat otomatis, serta peningkatan fitur keamanan dibandingkan dengan IPv4.

## Langkah-Langkah

1. Buka file IPv6_sample menggunakan wireshark
2. setelah terbuka ketik ipv6 pada kolom filter
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6f7b291f-a9d0-4a07-9bf0-752c39a1bdd7" />

Berdasarkan hasil capture menggunakan Wireshark, terlihat adanya komunikasi jaringan yang menggunakan protokol IPv6 (Internet Protocol Version 6). Hal ini dapat diketahui dari alamat sumber 2001:db8:1::10 dan alamat tujuan 2a00:1450:4009:80b::... yang menggunakan format alamat IPv6. Paket yang diamati menggunakan protokol TCP dengan komunikasi dari port 52344 menuju port 443, yang umumnya digunakan untuk layanan HTTPS atau akses web yang aman. Pada kolom informasi juga terlihat keterangan TCP Retransmission, yang menunjukkan adanya pengiriman ulang paket karena paket sebelumnya belum diterima atau belum mendapatkan konfirmasi dari penerima. Selain itu, terdapat keterangan Previous segment not captured yang menandakan ada segmen data yang tidak berhasil direkam saat proses capture berlangsung. Dari hasil pengamatan tersebut dapat disimpulkan bahwa jaringan telah menggunakan IPv6 untuk melakukan komunikasi data dengan layanan HTTPS, serta terjadi beberapa retransmisi paket selama proses pertukaran data.
