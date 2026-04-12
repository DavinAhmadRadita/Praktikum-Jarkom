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
Tracking DNS dengan Wireshark adalah proses memantau dan menganalisis lalu lintas DNS di jaringan untuk melihat bagaimana sebuah domain diterjemahkan menjadi alamat IP. Secara sederhana, saat menggunakan Wireshark, kita bisa menangkap paket data DNS yang dikirim dari komputer ke server DNS, lalu melihat isi permintaan (query) dan jawaban (response) yang berisi alamat IP dari domain tersebut, sehingga berguna untuk troubleshooting jaringan atau analisis keamanan.

## Langkah - Langkah

1. Buka cmd lalu ketik "IPCONFIG" untuk melihat ip pada laptop, lalu copy ip nya dan buka wireshark
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21c47e43-8988-4e7c-a13e-1c3428747673" />

2. setelah membuka wireshark pilih jaringan yang digunakan, lalu tulis ip.addr == 10.225.197.205 pada search bar (ip nya sesuai hasil dari cmd)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b3d40781-2427-4ca5-8a0d-485755fd3ff6" />

3. selanjutnya buka link "http://www.ietf.org/" pada browser yang digunakan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7abf97e3-bcc4-4162-b282-4a8db4975889" />

4. ketik lagi ip.addr == 10.225.197.205 && dns.qry.name contains "ietf" pada search bar 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/17a4f193-44cb-42fa-8124-c147f26ad669" />

## Pertanyaan

1. Cari pesan permintaan DNS dan balasannya. Apakah pesan tersebut dikirimkan melalui UDP atau TCP?
2. Apa port tujuan pada pesan permintaan DNS? Apa port sumber pada pesan balasannya?
3. Pada pesan permintaan DNS, apa alamat IP tujuannya? Apa alamat IP server DNS lokal anda (gunakan ipconfig untuk mencari tahu)? Apakah kedua alamat IP tersebut sama?
4. Periksa pesan permintaan DNS. Apa “jenis” atau ”type” dari pesan tersebut? Apakah pesan permintaan tersebut mengandung ”jawaban” atau ”answers”?
5. Periksa pesan balasan DNS. Berapa banyak ”jawaban” atau ”answers” yang terdapat di dalamnya? Apa saja isi yang terkandung dalam setiap jawaban tersebut?
6. Perhatikan paket TCP SYN yang selanjutnya dikirimkan oleh host Anda. Apakah alamat IP pada paket tersebut sesuai dengan alamat IP yang tertera pada pesan balasan DNS?
7. Halaman web yang sebelumnya anda akses (http://www.ietf.org) memuat beberapa gambar. Apakah host Anda perlu mengirimkan pesan permintaan DNS baru setiap kali ingin mengakses suatu gambar?

## Jawaban

1. Berdasarkan hasil analisis pada Wireshark, pesan permintaan DNS (DNS query) dan pesan balasannya (DNS response) terlihat jelas pada daftar paket yang ditampilkan. Dari bagian detail paket, dapat diketahui bahwa protokol yang digunakan adalah User Datagram Protocol (UDP), bukan TCP. Hal ini sesuai dengan karakteristik umum DNS yang biasanya menggunakan UDP karena lebih ringan dan cepat untuk pertukaran data.
<img width="545" height="205" alt="image" src="https://github.com/user-attachments/assets/15669b6b-27ba-4bc8-84e1-84ac998b4458" />

2. Pada pesan permintaan DNS, port tujuan yang digunakan adalah port 53, yang merupakan port standar untuk layanan DNS. Sementara itu, port sumber pada pesan tersebut adalah port acak (ephemeral port) yang digunakan oleh client, yaitu 53453. Untuk pesan balasan DNS, port sumbernya adalah port 53 (dari server DNS), dan port tujuannya adalah port 53453, yaitu port milik client yang sebelumnya digunakan untuk mengirim permintaan.
<img width="222" height="41" alt="image" src="https://github.com/user-attachments/assets/b8ea9fae-e04a-499f-bb0a-6699f5bb2845" />

3. alamat IP tujuan pada pesan permintaan DNS adalah 10.225.197.204, sedangkan alamat IP sumbernya adalah 10.225.197.205, yang merupakan alamat IP dari host atau komputer yang digunakan. Dari hasil perintah ipconfig yang ditampilkan pada Command Prompt, konfigurasi jaringan menggunakan gateway dengan alamat IP 10.225.197.204, yang dalam jaringan ini juga berfungsi sebagai server DNS lokal.
<img width="1088" height="315" alt="image" src="https://github.com/user-attachments/assets/41a3fe99-2e96-43b8-982b-37191b32d918" />

4. pesan permintaan DNS yang saya analisis merupakan standard query dengan jenis (type) A (Address Record), yaitu permintaan untuk mengetahui alamat IP (IPv4) dari domain www.ietf.org. Selain itu, pada bagian detail paket terlihat bahwa nilai Answer RRs = 0, yang menunjukkan bahwa pesan permintaan tersebut tidak mengandung jawaban (answers). Hal ini karena paket tersebut merupakan permintaan dari client (komputer saya) ke server DNS, sehingga hanya berisi pertanyaan, sedangkan jawaban akan diberikan pada paket balasan DNS (response).
<img width="289" height="198" alt="image" src="https://github.com/user-attachments/assets/0255afdb-db04-4646-bfc8-3c45ef963742" />

5. Pada pesan balasan DNS (DNS response) yang saya analisis terdapat dua buah jawaban (answers). Hal ini dapat dilihat pada bagian Answer RRs yang menunjukkan jumlah record yang diberikan oleh server DNS. Setiap jawaban tersebut berisi informasi alamat IP yang terkait dengan domain yang saya akses, yaitu www.ietf.org. Adapun isi dari kedua jawaban tersebut adalah alamat IP 104.16.45.99 dan 104.16.44.99. Kedua alamat IP ini menunjukkan bahwa satu domain dapat memiliki lebih dari satu alamat IP, yang biasanya digunakan untuk tujuan load balancing atau meningkatkan ketersediaan layanan.
<img width="688" height="443" alt="image" src="https://github.com/user-attachments/assets/201cf1d7-f7fc-4896-a8ef-3c59cb94f8c9" />

6. setelah proses DNS selesai, komputer saya mengirimkan paket TCP SYN untuk memulai koneksi ke server tujuan. Pada hasil capture terlihat bahwa paket TCP SYN dikirim dari alamat IP 10.225.197.205 menuju alamat IP 104.16.45.99 dengan port tujuan 443 (HTTPS). Jika dibandingkan dengan hasil DNS response sebelumnya, alamat IP 104.16.45.99 merupakan salah satu alamat IP yang diberikan oleh server DNS untuk domain www.ietf.org. Dengan demikian, dapat disimpulkan bahwa alamat IP pada paket TCP SYN tersebut sesuai dengan alamat IP yang diperoleh dari pesan balasan DNS. Hal ini menunjukkan bahwa hasil resolusi DNS digunakan secara langsung oleh host saya untuk membangun koneksi ke server tujuan.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/490b18ba-aecb-493f-9dbe-037369caa3bc" />

7. host saya tidak selalu perlu mengirimkan pesan permintaan DNS baru setiap kali mengakses gambar. Hal ini karena sistem operasi dan browser biasanya menyimpan hasil resolusi DNS (DNS cache), sehingga jika domain yang diakses sama, maka alamat IP yang sudah diketahui sebelumnya dapat langsung digunakan tanpa perlu melakukan permintaan DNS ulang.
