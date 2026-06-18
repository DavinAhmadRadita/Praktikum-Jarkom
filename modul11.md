# MODUL 11 DHCP

**DHCP (Dynamic Host Configuration Protocol)** adalah protokol jaringan yang digunakan untuk memberikan alamat IP secara otomatis kepada perangkat yang terhubung ke jaringan. Dengan DHCP, pengguna tidak perlu mengatur alamat IP secara manual karena server DHCP akan secara otomatis memberikan konfigurasi jaringan seperti alamat IP, subnet mask, default gateway, dan DNS server kepada perangkat yang meminta koneksi. DHCP memudahkan pengelolaan jaringan, mengurangi kemungkinan terjadinya konflik alamat IP, serta mempercepat proses koneksi perangkat ke jaringan baik pada jaringan lokal maupun internet.

## Fungsi DHCP

**Fungsi DHCP (Dynamic Host Configuration Protocol)** untuk memberikan konfigurasi jaringan secara otomatis kepada perangkat yang terhubung ke jaringan. DHCP akan menetapkan alamat IP, subnet mask, default gateway, dan DNS server tanpa perlu pengaturan manual oleh pengguna. Dengan adanya DHCP, proses koneksi perangkat ke jaringan menjadi lebih cepat, pengelolaan alamat IP menjadi lebih mudah, serta dapat mengurangi risiko terjadinya konflik alamat IP antar perangkat dalam jaringan.

## Kelebihan DHCP

- Memberikan alamat IP secara otomatis kepada perangkat.
- Mempermudah pengelolaan jaringan.
- Menghemat waktu konfigurasi jaringan.
- Mengurangi kesalahan konfigurasi IP secara manual.
- Mencegah terjadinya konflik alamat IP antar perangkat.
- Memudahkan penambahan perangkat baru ke jaringan.
- Dapat mengelola alamat IP secara terpusat melalui server DHCP.

# Kekurangan DHCP

- Bergantung pada ketersediaan server DHCP.
- Jika server DHCP mengalami gangguan, perangkat baru tidak dapat memperoleh alamat IP.
- Memerlukan konfigurasi dan pengelolaan server DHCP.
- Berpotensi menimbulkan risiko keamanan jika terdapat DHCP Server palsu (Rogue DHCP).
- Kurang cocok untuk perangkat yang membutuhkan alamat IP tetap (static IP), seperti server atau printer jaringan.
- Jika terjadi kesalahan konfigurasi pada server DHCP, seluruh klien dapat menerima konfigurasi jaringan yang salah.

# DORA

**DORA (Discover, Offer, Request, Acknowledge)** adalah proses yang digunakan oleh DHCP untuk memberikan alamat IP secara otomatis kepada perangkat yang terhubung ke jaringan. Proses ini dimulai ketika perangkat mengirim pesan DHCP Discover untuk mencari server DHCP yang tersedia. Setelah menerima permintaan tersebut, server DHCP akan membalas dengan DHCP Offer yang berisi tawaran alamat IP dan konfigurasi jaringan lainnya. Selanjutnya, perangkat akan mengirim DHCP Request untuk meminta penggunaan alamat IP yang ditawarkan oleh server. Terakhir, server DHCP mengirim DHCP Acknowledge (ACK) sebagai konfirmasi bahwa alamat IP tersebut telah diberikan dan dapat digunakan oleh perangkat. Setelah proses DORA selesai, perangkat dapat berkomunikasi dalam jaringan menggunakan konfigurasi yang telah diterima dari server DHCP.

## Langkah-Langkah

1. download file http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip lalu ekstrak
2. setelah di ekstrak buka file tersebut ke dalam wireshark dan ketik dhcp pada kolom filter
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3ece5968-7001-4fc1-aa67-c5d6bf0f8883" />

## Tahapan DORA pada DHCP

**Discover (DHCP Discover)**
- Perangkat (client) mengirimkan pesan broadcast untuk mencari server DHCP yang tersedia di jaringan.

**Offer (DHCP Offer)**
- Server DHCP merespons dengan menawarkan alamat IP beserta informasi jaringan lainnya, seperti subnet mask, gateway, dan DNS.

**Request (DHCP Request)**
- Client mengirimkan permintaan kepada server DHCP untuk menggunakan alamat IP yang telah ditawarkan.

**Acknowledge (DHCP ACK)**
- Server DHCP mengirimkan konfirmasi bahwa alamat IP telah diberikan dan dapat digunakan oleh client.

Urutan DORA:
Discover → Offer → Request → Acknowledge (ACK).
