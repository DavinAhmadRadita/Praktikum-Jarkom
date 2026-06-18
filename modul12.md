<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/258d4daa-f9d0-4af6-a533-e88a2f961e6f" /># MODUL 12 ICMP

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
2. setelah itu buka cmd lalu ketik ping -n 10 www.ust.hk
<img width="737" height="436" alt="image" src="https://github.com/user-attachments/assets/eb3ccb48-b9d4-4b2e-9759-19da456b8a34" />

3. setelah seleai proses nya stop capture pada wirechark
4. lalu ketik icmp pada kolom search
5. pilih salah satu packet ICMP Echo Reply dan expand
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/95642da8-29a3-4772-b4d3-e4d207b1462c" />

6. pilih salah satu packet ICMP Echo Request dan expand
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a3ddebc6-8d47-4f64-b17b-ad1885d9254b" />

