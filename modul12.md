# MODUL 12 ICMP

**ICMP (Internet Control Message Protocol)** adalah protokol jaringan yang digunakan untuk mengirimkan pesan kontrol, informasi status, dan laporan kesalahan antar perangkat dalam jaringan IP. ICMP tidak digunakan untuk mengirim data pengguna, melainkan untuk membantu proses komunikasi dan diagnosis jaringan. Protokol ini sering digunakan pada perintah ping untuk menguji konektivitas antara dua perangkat dan traceroute untuk melacak jalur yang dilalui paket data menuju tujuan. Dengan ICMP, administrator jaringan dapat mendeteksi masalah koneksi, mengetahui apakah suatu perangkat dapat dijangkau, serta menganalisis kinerja jaringan.

## Fungsi ICMP

- Mengirim pesan kesalahan (error message) pada jaringan.
- Menguji konektivitas antar perangkat dalam jaringan.
- Membantu proses diagnosis dan troubleshooting jaringan.
- Mengetahui apakah suatu host atau perangkat dapat dijangkau.

## ICMP digunakan untuk

- Mengecek apakah suatu perangkat dapat dihubungi dalam jaringan (ping).
- Melacak jalur yang dilalui paket data menuju tujuan (traceroute).
- Mengirim pesan kesalahan ketika terjadi masalah dalam pengiriman paket.
- Memberikan informasi status dan kondisi jaringan.

## Langkah-Langkah

1. Buka wireshark lalu pilih wifi
2. setelah itu buka cmd lalu ketik "ping -n 10 www.ust.hk"
<img width="737" height="436" alt="image" src="https://github.com/user-attachments/assets/eb3ccb48-b9d4-4b2e-9759-19da456b8a34" />

3. setelah seleai proses nya stop capture pada wirechark
4. lalu ketik icmp pada kolom search
5. pilih salah satu packet ICMP Echo Request dan expand
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5c36f3cb-60b1-4b35-8d72-99e67bbdf7e7" />

6. pilih salah satu packet ICMP Echo Reply dan expand
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7c67cb52-ae0e-41c8-859f-9b30f7d607df" />

## Analaisis

<img width="1912" height="671" alt="image" src="https://github.com/user-attachments/assets/046d95c3-95e4-4559-bc7c-5fb306d35fc8" />

Program ping menghasilkan dua jenis pesan ICMP, yaitu ICMP Echo Request dan ICMP Echo Reply. Berdasarkan hasil capture pada Wireshark, terlihat bahwa setiap paket Echo Request yang dikirim dari alamat IP 10.144.53.204 menuju 143.89.209.9 selalu mendapatkan balasan berupa Echo Reply dari 143.89.209.9 kembali ke 10.144.53.204. Pada data yang ditampilkan terdapat 10 paket Echo Request dan 10 paket Echo Reply, sehingga total paket ICMP yang berhasil tercapture adalah 20 paket. Hal ini menunjukkan bahwa komunikasi antara kedua host berlangsung dengan baik karena setiap permintaan ping mendapatkan respons dari host tujuan. Selain itu, paket Echo Request memiliki nilai TTL 128, sedangkan paket Echo Reply memiliki nilai TTL 45, yang menunjukkan bahwa paket balasan telah melewati beberapa router sebelum sampai ke pengirim.

**ICMP Echo Request**

<img width="397" height="207" alt="image" src="https://github.com/user-attachments/assets/57da632a-ac31-4f08-b037-e5eea8734afa" />

- Type = Echo (ping) request (8) → menunjukkan bahwa paket ICMP tersebut merupakan Echo Request, yaitu permintaan ping yang dikirim oleh host sumber ke host tujuan untuk menguji konektivitas jaringan.
- Code = 0 → menunjukkan bahwa tidak terdapat informasi atau kondisi khusus tambahan pada pesan ICMP Echo Request tersebut.
- Checksum = 0x4d5a [correct] → menunjukkan bahwa nilai checksum valid, sehingga paket diterima tanpa mengalami kesalahan atau kerusakan data selama proses transmisi.
- Identifier (BE) = 1 (0x0001) → berfungsi sebagai identitas paket ICMP yang digunakan untuk mencocokkan paket Echo Reply dengan Echo Request yang sesuai.
- Sequence Number (BE) = 1 (0x0001) → menunjukkan bahwa paket tersebut merupakan paket ping pertama yang dikirim dalam sesi komunikasi tersebut.
- Response Frame = 652 → menunjukkan bahwa balasan (Echo Reply) untuk paket Echo Request ini terdapat pada frame nomor 652 di hasil capture Wireshark.

**ICMP Echo Reply**

<img width="372" height="237" alt="image" src="https://github.com/user-attachments/assets/c4d3d700-a34e-4fa1-a294-4568e8624202" />

- Type = Echo (ping) reply (0) → menunjukkan bahwa paket ICMP tersebut merupakan Echo Reply, yaitu balasan dari host tujuan terhadap permintaan ping (Echo Request) yang diterima sebelumnya.
- Code = 0 → menunjukkan bahwa paket Echo Reply tidak mengandung informasi kesalahan atau kondisi khusus tambahan.
- Checksum = 0x555a [correct] → menunjukkan bahwa nilai checksum valid, sehingga paket diterima dengan baik tanpa mengalami kerusakan data selama transmisi.
- Identifier (BE) = 1 (0x0001) → berfungsi sebagai identitas paket yang digunakan untuk mencocokkan Echo Reply dengan Echo Request yang sesuai.
- Sequence Number (BE) = 1 (0x0001) → menunjukkan bahwa paket balasan ini merupakan respons untuk paket ping pertama yang dikirim oleh pengirim.
- Request Frame = 646 → menunjukkan bahwa paket Echo Request yang terkait dengan balasan ini berada pada frame nomor 646 di hasil capture Wireshark.
- Response Time = 94.626 ms → menunjukkan waktu yang dibutuhkan sejak Echo Request dikirim hingga Echo Reply diterima kembali, yaitu sekitar 94,626 milidetik.
- Data (32 bytes) → menunjukkan bahwa paket Echo Reply membawa data sebesar 32 byte, yang sama dengan data yang dikirim pada paket Echo Request.

# Analisis ICMP yang Dihasilkan Oleh Traceroute

1. Buka wireshark lalu pilih wifi
2. setelah itu buka cmd lalu ketik "tracert www.ust.hk"
<img width="987" height="641" alt="image" src="https://github.com/user-attachments/assets/369b124c-933f-49f1-bc12-05b5eb7a7082" />

3. Setelah proses tracert pada cmd selesai lakukan stop capture pada wireshark
4. Lalu ketik icmp pada search bar
5. Pilih dan expand salah satu packet ICMP Echo Request
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/29c0c064-70b9-4280-893a-5a79905806e6" />

6. Pilih dan expand salah satu packet Time To Live (TTL)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3da2c427-a33b-4259-9539-f02e5153f885" />

## Analisis

**Pesan ICMP yang dihasilkan oleh program tracerout**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/283e86af-41da-4d4a-9624-1d01e8a47dff" />

- ICMP Echo Request merupakan paket ICMP yang dikirim dari alamat IP 10.144.53.204 menuju 143.89.209.9 untuk menguji konektivitas jaringan. Pada capture terlihat beberapa Echo Request dikirim dengan nilai TTL yang berbeda-beda (TTL=1, TTL=2, TTL=3, dan TTL=4) sebagai bagian dari proses pelacakan jalur paket.
- ICMP Time Exceeded (Time to Live Exceeded in Transit) merupakan pesan ICMP yang dikirim oleh router, seperti 10.144.53.2, 10.4.8.105, dan 114.0.63.73, ketika nilai TTL (Time To Live) pada paket telah habis sebelum paket berhasil mencapai tujuan. Pesan ini menunjukkan bahwa paket dihentikan oleh router karena telah melewati batas hop yang diizinkan.

**ICMP Echo Request**
<img width="960" height="222" alt="image" src="https://github.com/user-attachments/assets/a4a1e834-3371-427d-90fe-0bfa452baf5e" />

- Type = Echo (ping) request (8) → menunjukkan bahwa paket ICMP tersebut merupakan Echo Request, yaitu permintaan ping yang dikirim dari host sumber ke host tujuan untuk menguji konektivitas jaringan.
- Code = 0 → menunjukkan bahwa paket Echo Request tidak memiliki informasi tambahan atau indikasi kesalahan pada pesan ICMP.
- Checksum = 0xf7f0 [correct] → menunjukkan bahwa nilai checksum valid, sehingga paket dapat diterima tanpa mengalami kerusakan data selama proses transmisi.
- Identifier (BE) = 1 (0x0001) → berfungsi sebagai identitas paket ICMP yang digunakan untuk mencocokkan paket Echo Request dengan balasan Echo Reply yang diterima.
- Sequence Number (BE) = 14 (0x000e) → menunjukkan bahwa paket tersebut merupakan paket ping urutan ke-14 yang dikirim dalam sesi komunikasi.
- No response seen → menunjukkan bahwa pada hasil capture Wireshark tidak ditemukan paket Echo Reply yang menjadi balasan untuk Echo Request tersebut. Hal ini dapat terjadi karena paket diblokir, hilang di jaringan, atau memang tidak mendapatkan respons dari host tujuan.
- Data (64 bytes) → menunjukkan bahwa paket Echo Request membawa data sebesar 64 byte yang dikirim bersama pesan ICMP.

**ICMP Time Exceeded**
<img width="957" height="351" alt="image" src="https://github.com/user-attachments/assets/eee5fa22-fc26-44a3-9672-e0479984ac5e" />

- Type = Time-to-live exceeded (11) → menunjukkan bahwa paket ICMP tersebut merupakan pesan Time Exceeded yang dikirim oleh router karena nilai TTL (Time To Live) pada paket telah habis sebelum mencapai host tujuan.
- Code = 0 (Time to live exceeded in transit) → menunjukkan bahwa TTL paket habis selama proses perjalanan di jaringan sehingga paket tidak dapat diteruskan ke tujuan berikutnya.
- Checksum = 0xf4ff [correct] → menunjukkan bahwa nilai checksum valid dan paket diterima tanpa mengalami kerusakan data selama transmisi.
- Unused = 00000000 → merupakan field yang tidak digunakan pada pesan ICMP Time Exceeded dan bernilai nol.
- Internet Protocol Version 4, Src: 10.144.53.204, Dst: 143.89.209.9 → menunjukkan informasi paket asli yang menyebabkan terjadinya pesan Time Exceeded, yaitu paket yang dikirim dari 10.144.53.204 menuju 143.89.209.9.
- Type = Echo (ping) request (8) → menunjukkan bahwa paket asli yang TTL-nya habis merupakan paket ICMP Echo Request (ping).
- Identifier (BE) = 1 (0x0001) → digunakan sebagai identitas paket ICMP agar dapat dibedakan dari paket lainnya.
- Sequence Number (BE) = 14 (0x000e) → menunjukkan bahwa paket yang mengalami TTL habis adalah paket ping urutan ke-14.
- Data (64 bytes) → menunjukkan bahwa paket Echo Request yang dikirim membawa data sebesar 64 byte.
