# Modul 6 TCP

TCP (Transmission Control Protocol) adalah protokol komunikasi dalam jaringan komputer yang digunakan untuk mengirim data secara andal dan teratur antar perangkat. Berbeda dengan UDP, TCP memastikan bahwa data yang dikirim sampai ke tujuan dengan lengkap dan dalam urutan yang benar melalui proses pengecekan, pengiriman ulang jika terjadi kesalahan, serta adanya koneksi antara pengirim dan penerima.

## 6.2 Menangkap Tansfer TCP dalam Jumlah Besar dari Komputer Pribadi ke Remote Server

Menangkap transfer TCP dalam jumlah besar dari komputer pribadi ke remote server adalah proses memantau dan merekam lalu lintas data yang dikirim melalui protokol TCP dari perangkat lokal ke server tujuan menggunakan tools seperti Wireshark. Dalam proses ini, Wireshark digunakan untuk menangkap paket-paket TCP yang lewat di jaringan, kemudian menampilkannya secara detail, mulai dari alamat IP sumber dan tujuan, port yang digunakan, hingga isi data yang dikirim. Dengan menangkap data dalam jumlah besar, kita dapat menganalisis performa jaringan, mendeteksi masalah seperti packet loss atau delay, serta mengidentifikasi aktivitas yang mencurigakan atau tidak normal pada koneksi antara komputer dan server.

## Langkah - Langkah

1. buka link " http://gaia.cs.umass.edu/wireshark-labs/alice.txt" pada browser, lalu save dengan cara click kanan lalu pilih save as
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/28d6484f-4ca1-41c3-a7bc-f1788b6f161e" />

2. Selanjutnya buka link "http://gaia.cs.umass.edu/wireshark-labs/TCP-wireshark-file1.html"
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7c16c3df-7445-40d0-b4b4-40a63f3a6b6f" />

3. Setelah itu pilih file yang sudah di save tadi dan upload, Setelah upload maka akan muncul seperti di gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f0bf5ed5-88c2-47a4-9a49-9f590574b869" />

4. Stop capture wireshark dan ketik tcp pada search bar
<img width="1235" height="44" alt="image" src="https://github.com/user-attachments/assets/7c5f31d1-43ba-43b9-81ac-cf7c7c4e73d7" />

Paket SYN berfungsi untuk memulai koneksi TCP antara client dan server melalui proses three-way handshake, bukan untuk mengirimkan file. Proses ini bertujuan memastikan bahwa koneksi sudah siap digunakan sebelum dilakukan pertukaran data. Setelah koneksi berhasil terbentuk, file akan dikirim dalam bentuk beberapa segmen kecil melalui TCP. Hal ini dilakukan karena TCP membagi data menjadi bagian-bagian kecil agar proses pengiriman lebih efisien

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5688f682-6030-4dbd-9546-3596bb4cb04a" />
Setelah proses upload selesai, server akan memberikan respon HTTP/1.1 200 OK. Respon ini menunjukkan bahwa file telah berhasil diterima dan diproses oleh server.

## 6.3 Tampilan Awal pada Captured Trace

## Pertanyaan
1. Berapa alamat IP dan nomor port TCP yang digunakan oleh komputer klien (sumber) untuk mentransfer file ke gaia.cs.umass.edu? Cara paling mudah menjawab pertanyaan ini adalah dengan memilih sebuah pesan HTTP dan meneliti detail paket TCP yang digunakan untuk membawa pesan HTTP tersebut.
2. Apa alamat IP dari gaia.cs.umass.edu? Pada nomor port berapa ia mengirim dan menerima segmen TCP untuk koneksi ini?
3. Berapa alamat IP dan nomor port TCP yang digunakan oleh komputer klien Anda (sumber) untuk mentransfer ke gaia.cs.umass.edu?

## Jawaban

1. Alamat IP komputer klien yang digunakan untuk mentransfer file ke gaia.cs.umass.edu adalah 10.225.197.205 dengan nomor port TCP 56333.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9844423e-09f6-4349-9a9b-83026f1db04a" />

2. Alamat IP dari gaia.cs.umass.edu adalah 128.119.245.12 dan server tersebut menggunakan port TCP 80 untuk mengirim dan menerima segmen TCP pada koneksi ini.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ae2ad143-7b28-40f5-8408-22d74462ef6f" />

3. Alamat IP komputer klien saya adalah 10.225.197.205 dan menggunakan nomor port TCP 56333 untuk mentransfer data ke gaia.cs.umass.edu.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5dc361e1-012f-4c9b-9447-413927b912ec" />

## 6.4 Dasar TCP

## Pertanyaan

1. Berapa nomor urut segmen TCP SYN yang digunakan untuk memulai sambungan TCP antara komputer klien dan gaia.cs.umass.edu? Apa yang dimiliki segmen tersebut sehingga teridentifikasi sebagai segmen SYN? 
2. Berapa nomor urut segmen SYNACK yang dikirim oleh gaia.cs.umass.edu ke komputer klien sebagai balasan dari SYN? Berapa nilai dari field Acknowledgement pada segmen SYNACK? Bagaimana gaia.cs.umass.edu menentukan nilai tersebut? Apa yang dimiliki oleh segmen sehingga teridentifikasi sebagai segmen SYNACK? 
3. Berapa nomor urut segmen TCP yang berisi perintah HTTP POST? Perhatikan bahwa untuk menemukan perintah POST, Anda harus menelusuri content field milik paket di bagian bawah jendela Wireshark, kemudian cari segmen yang berisi "POST" di bagian field DATAnya. 
4. Anggap segmen TCP yang berisi HTTP POST sebagai segmen pertama dalam koneksi TCP. Berapa nomor urut dari enam segmen pertama dalam TCP (termasuk segmen yang berisi HTTP POST)? Pada jam berapa setiap segmen dikirim? Kapan ACK untuk setiap segmen diterima? Dengan adanya perbedaan antara kapan setiap segmen TCP dikirim dan kapan acknowledgement-nya diterima, berapakah nilai RTT untuk keenam segmen tersebut? Berapa nilai EstimatedRTT setelah penerimaan setiap ACK? (Catatan: Wireshark memiliki fitur yang memungkinkan Anda untuk memplot RTT untuk setiap segmen TCP yang dikirim. Pilih segmen TCP yang dikirim dari klien ke server gaia.cs.umass.edu pada jendela "daftaraket yang ditangkap". Kemudian pilih: Statistics->TCP Stream Graph- >Round Trip Time Graph). 
5. Berapa panjang setiap enam segmen TCP pertama? 
6. Berapa jumlah minimum ruang buffer tersedia yang disarankan kepada penerima dan diterima untuk seluruh trace? Apakah kurangnya ruang buffer penerima pernah menghambat pengiriman? 
7. Apakah ada segmen yang ditransmisikan ulang dalam file trace? Apa yang anda periksa (di dalam file trace) untuk menjawab pertanyaan ini? 
8. Berapa banyak data yang biasanya diakui oleh penerima dalam ACK? Dapatkah anda mengidentifikasi kasus-kasus di mana penerima melakukan ACK untuk setiap segmen yang diterima? 
9. Berapa throughput (byte yang ditransfer per satuan waktu) untuk sambungan TCP? Jelaskan bagaimana Anda menghitung nilai ini.

# Jawaban

1. Nomor urut (Sequence Number) pada segmen SYN adalah Seq = 0. Segmen ini dikenali sebagai SYN karena pada kolom info terdapat [SYN], yang berarti flag SYN aktif (1) dan digunakan untuk memulai koneksi TCP.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/96ed1df8-b068-48c1-b496-d9a2cff88926" />

2. Nomor urut (Sequence Number) pada segmen SYN-ACK adalah Seq = 0, sedangkan nilai Acknowledgement Number = 1. Nilai Acknowledgement tersebut diperoleh dari nomor urut segmen SYN milik klien (Seq = 0) yang kemudian ditambah 1, karena dalam TCP, segmen SYN dianggap mengonsumsi satu nomor urut. Segmen ini dapat diidentifikasi sebagai segmen SYN-ACK karena pada bagian Flags terlihat [SYN, ACK], yang berarti kedua flag tersebut aktif (set).
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3304d98f-3264-4c73-88da-978bce24213f" />

3. Nomor urut (Sequence Number) segmen TCP yang berisi perintah HTTP POST adalah Seq = 1. Segmen ini ditemukan pada frame nomor 4, yang dapat diidentifikasi dengan melihat isi payload pada bagian data yang mengandung teks "POST /ethereal-labs/lab3-1-reply.htm HTTP/1.1". Selain itu, segmen ini juga memiliki flag [PSH, ACK] dengan panjang data Len = 565 byte, yang menunjukkan bahwa segmen tersebut membawa data aplikasi (HTTP POST).
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9e4e8664-6896-4751-9002-29c06b03f519" />
