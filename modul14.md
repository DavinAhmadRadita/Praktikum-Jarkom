# MODUL 14 WIFI

Wi-Fi merupakan teknologi jaringan nirkabel yang mengacu pada standar IEEE 802.11. Standar ini dikembangkan oleh Institute of Electrical and Electronics Engineers (IEEE) untuk mengatur komunikasi data antar perangkat melalui gelombang radio tanpa menggunakan kabel. IEEE 802.11 memastikan bahwa berbagai perangkat Wi-Fi, seperti laptop, smartphone, dan access point, dapat saling terhubung dan berkomunikasi dengan baik meskipun berasal dari produsen yang berbeda. Standar ini mencakup dua komponen utama, yaitu Physical Layer (PHY) yang mengatur proses pengiriman dan penerimaan sinyal radio, serta Media Access Control (MAC) Layer yang mengatur mekanisme akses perangkat ke media jaringan. Dengan adanya standar IEEE 802.11, komunikasi nirkabel dapat berlangsung secara stabil, efisien, dan kompatibel sehingga mendukung koneksi internet yang cepat dan handal.

## Perbandingan Frekuensi Wifi

**Frekuensi 2,4 GHz**

Kelebihan:

- Memiliki jangkauan sinyal yang lebih luas dibandingkan frekuensi 5 GHz.
- Lebih efektif dalam menembus tembok dan berbagai penghalang fisik.
- Cocok digunakan pada area yang luas atau memiliki banyak ruangan.

Kekurangan:

- Kecepatan transfer data relatif lebih rendah.
- Rentan terhadap interferensi dari perangkat lain seperti Bluetooth, microwave, dan perangkat Wi-Fi lainnya.
- Kinerja jaringan dapat menurun ketika banyak perangkat menggunakan frekuensi yang sama.

**Frekuensi 5 GHz**

Kelebihan:

- Menyediakan kecepatan transfer data yang lebih tinggi.
- Memiliki jumlah channel yang lebih banyak sehingga mengurangi kemungkinan terjadinya interferensi.
- Cocok untuk aktivitas yang membutuhkan bandwidth besar, seperti streaming video dan game online.

Kekurangan:

- Jangkauan sinyal lebih pendek dibandingkan frekuensi 2,4 GHz.
- Sinyal lebih sulit menembus dinding atau penghalang fisik lainnya.
- Kualitas koneksi dapat menurun pada jarak yang jauh dari access point.

Access Point (AP)

Access Point (AP) adalah perangkat jaringan yang berfungsi untuk menyediakan dan menyebarkan sinyal Wi-Fi kepada perangkat nirkabel. AP menghubungkan perangkat seperti laptop, smartphone, dan tablet ke jaringan lokal maupun internet tanpa menggunakan kabel. Selain itu, access point juga dapat digunakan untuk memperluas jangkauan jaringan Wi-Fi sehingga area yang sebelumnya sulit mendapatkan sinyal dapat terhubung ke jaringan dengan lebih baik.

## Analisis Beacon Frame

Pada percobaan kali ini menggunakan file capture yang telah digunakan pada praktikum sebelumnya. File tersebut terlebih dahulu diekstrak dari format ZIP, lalu buka aplikasi Wireshark. Setelah file berhasil di open, masukkan filter wlan.fc.subtype == 8 && wlan.fc.type == 0 pada search bar.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1ffc1331-2439-47b6-81fb-efad81d4ee67" />

Berdasarkan hasil capture pada Wireshark setelah menerapkan filter wlan.fc.subtype == 8 && wlan.fc.type == 0, terlihat sejumlah paket Beacon Frame yang dikirim oleh access point secara berkala. Pada kolom Info terlihat beberapa Beacon Frame dengan Beacon Interval (BI) = 100 dan SSID seperti "30 Munroe St" serta "linksys12". Dari informasi yang ditampilkan, terdapat 2364 paket yang berhasil dicapture, dengan 762 paket Beacon Frame yang sesuai dengan filter dan ditampilkan pada layar. Beacon Frame ini digunakan oleh access point untuk mengumumkan keberadaan jaringan Wi-Fi serta memberikan informasi jaringan kepada perangkat yang berada di sekitarnya agar dapat menemukan dan terhubung ke jaringan tersebut.
<img width="960" height="602" alt="image" src="https://github.com/user-attachments/assets/2329d671-40cc-4366-8ac5-c1be0f9398f7" />

**Berdasarkan hasil ekspansi detail paket pada Frame 3, diperoleh informasi sebagai berikut:**
- PHY Type = 802.11b (HR/DSSS) menunjukkan bahwa jaringan Wi-Fi menggunakan standar fisik IEEE 802.11b dengan teknologi modulasi High-Rate Direct Sequence Spread Spectrum (HR/DSSS).
- Short Preamble = False menandakan bahwa access point menggunakan Long Preamble untuk proses sinkronisasi frame, sehingga lebih kompatibel dengan perangkat lama.
- Data Rate = 1.0 Mb/s menunjukkan bahwa Beacon Frame dikirim dengan kecepatan transmisi sebesar 1 Mbps.
- Channel = 6 dan Frequency = 2437 MHz menunjukkan bahwa access point beroperasi pada kanal 6 di pita frekuensi 2,4 GHz.
- Signal Strength = -30 dBm menunjukkan bahwa sinyal yang diterima sangat kuat dan kualitas koneksi berada dalam kondisi sangat baik.
- Noise Level = -100 dBm menunjukkan tingkat gangguan sinyal yang sangat rendah pada jaringan.
- Signal/Noise Ratio = 70 dB menunjukkan perbandingan yang sangat baik antara kekuatan sinyal dan tingkat gangguan, sehingga kualitas komunikasi jaringan menjadi lebih stabil.

**Analisis Tagged Parameters**
- SSID Parameter Set = "30 Munroe St" menunjukkan nama jaringan Wi-Fi (SSID) yang dipancarkan oleh access point.
- Supported Rates = 1, 2, 5.5, dan 11 Mbps menunjukkan kecepatan dasar yang didukung oleh access point sesuai standar IEEE 802.11b.
- DS Parameter Set = Current Channel: 6 menunjukkan bahwa jaringan menggunakan kanal 6 sebagai kanal operasional.
- Traffic Indication Map (TIM) digunakan untuk memberikan informasi kepada perangkat yang terhubung mengenai data yang menunggu untuk dikirim oleh access point.
- Country Information = US, Environment Indoor menunjukkan bahwa perangkat dikonfigurasi untuk wilayah Amerika Serikat dan digunakan pada lingkungan dalam ruangan (indoor).
- Extended Supported Rates = 6, 9, 12, 18, 24, 36, 48, dan 54 Mbps menunjukkan kecepatan tambahan yang didukung oleh access point pada standar Wi-Fi yang lebih baru.
- Vendor Specific: Airgo Networks, Inc. menunjukkan adanya informasi tambahan yang disediakan oleh vendor perangkat jaringan.
- Vendor Specific: Microsoft Corp. WMM/WME Parameter Element menunjukkan dukungan terhadap fitur Wi-Fi Multimedia (WMM) yang digunakan untuk meningkatkan kualitas layanan (QoS) pada trafik suara, video, dan data.

## Analisis Data Transfer

Untuk menganalisis perpindahan data, diterapkan filter alamat IP server: Untuk menganalisis perpindahan data, diterapkan filter alamat IP server:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fbc128b8-b4d9-44ae-bb48-e9012a9b0a51" />

Berdasarkan hasil capture Wireshark, terlihat proses pembentukan koneksi TCP antara host 192.168.1.109 dan server 128.119.245.12 melalui tahapan Three-Way Handshake, yaitu SYN, SYN-ACK, dan ACK. Setelah koneksi berhasil dibangun, pada Frame 480 terlihat paket HTTP GET /wireshark-labs/alice.txt HTTP/1.1 yang digunakan oleh klien untuk meminta file alice.txt dari server. Server kemudian merespons permintaan tersebut dengan mengirimkan data melalui beberapa segmen TCP yang terlihat pada frame-frame berikutnya.

Pada detail paket juga terlihat bahwa data melewati lapisan Logical Link Control (LLC), kemudian diteruskan menggunakan Internet Protocol Version 4 (IPv4). Komunikasi berlangsung dari alamat IP sumber 192.168.1.109 menuju alamat IP tujuan 128.119.245.12. Selain itu, komunikasi menggunakan port sumber 2538 dan port tujuan 80, yang merupakan port standar untuk layanan HTTP. Dari hasil pengamatan tersebut dapat disimpulkan bahwa klien berhasil membuat koneksi TCP dengan server dan mengirim permintaan HTTP untuk mengunduh file alice.txt.

## Analisis Proses Association & Disassociation

- **Association (Asosiasi)** merupakan proses ketika perangkat klien mulai terhubung ke sebuah Access Point (AP) pada jaringan Wi-Fi. Pada tahap ini, perangkat mengirimkan permintaan koneksi kepada Access Point, kemudian Access Point akan memberikan tanggapan berupa penerimaan atau penolakan terhadap permintaan tersebut. Jika permintaan diterima, perangkat klien dapat bergabung dan berkomunikasi melalui jaringan nirkabel yang tersedia.

- **Disassociation (Disasosiasi)** adalah proses pemutusan hubungan antara perangkat klien dan Access Point yang sebelumnya terhubung. Proses ini dapat terjadi karena perangkat klien secara sengaja memutus koneksi, berpindah ke Access Point lain saat melakukan roaming, atau karena Access Point menghentikan koneksi akibat kondisi tertentu seperti perubahan pengaturan jaringan, kualitas sinyal yang menurun, maupun alasan manajemen jaringan lainnya.

- Pada percobaan ini, proses manajemen koneksi pada jaringan Wi-Fi diamati menggunakan filter wlan.fc.type_subtype == 0 pada Wireshark. Filter tersebut digunakan untuk menampilkan paket-paket yang berkaitan dengan proses Association Request, sehingga aktivitas koneksi antara perangkat klien dan Access Point dapat dianalisis. Melalui paket yang ditampilkan, dapat diamati bagaimana perangkat klien mengajukan permintaan untuk bergabung ke jaringan nirkabel sebelum proses komunikasi data dapat dilakukan.

- **Expand Packet Awal**
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8bd25b07-82bd-40cb-83f6-c77b0f15547b" />

- **Expand Packet Akhir**
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9c3bf444-659a-461a-9d3f-59d0b00aa71e" />

- Frame 1750: Klien Intel_d1:b6:4f mengirimkan Association Request kepada Access Point CiscoLinksys_f5:ba:bb dengan SSID "linksys_SES_24086". Paket ini menunjukkan bahwa perangkat sedang berusaha melakukan proses asosiasi untuk bergabung ke jaringan Wi-Fi tersebut. Pada paket juga terlihat informasi keamanan WPA Information Element yang digunakan dalam proses koneksi.
- Frame 2162: Klien Intel_d1:b6:4f mengirimkan Association Request kepada Access Point CiscoLinksys_f7:1d:51 dengan SSID "30 Munroe St". Paket ini menunjukkan bahwa perangkat melakukan permintaan asosiasi ke jaringan Wi-Fi yang berbeda dari sebelumnya. Selain itu, paket menampilkan dukungan QoS Capability serta daftar Supported Rates dan Extended Supported Rates hingga 54 Mbps.

Kesimpulan: Perbedaan utama antara kedua paket terdapat pada SSID dan Access Point yang dituju. Pada Frame 1750 perangkat mencoba terhubung ke jaringan "linksys_SES_24086", sedangkan pada Frame 2162 perangkat mengirimkan permintaan asosiasi ke jaringan "30 Munroe St". Perubahan ini menunjukkan bahwa klien berpindah atau mencoba terhubung ke Access Point yang berbeda dalam jaringan Wi-Fi.

**Tanggapan Asosiasi (Association Response) dianalisis melalui filter subtype respon: wlan.fc.type_subtype == 1**
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/047a9c30-7a7a-4e77-bc73-fb29e18fe3ef" />

Ditemukan Frame 2166 yang merupakan paket Association Response. Pada frame ini, alamat pengirim (Transmitter Address dan Source Address) adalah CiscoLinksys_f7:1d:51, sedangkan alamat tujuan (Receiver Address dan Destination Address) adalah Intel_d1:b6:4f. Hal ini menunjukkan bahwa Access Point mengirimkan respons kepada perangkat klien setelah menerima permintaan asosiasi yang sebelumnya dikirimkan. Dengan adanya paket ini, proses asosiasi antara klien dan Access Point berhasil dilakukan.

Berdasarkan detail paket, Access Point mengirimkan informasi mengenai kecepatan transmisi yang didukung melalui parameter Supported Rates dan Extended Supported Rates, yaitu mulai dari 1 Mbps hingga 54 Mbps. Selain itu, paket juga memuat EDCA Parameter Set yang berfungsi untuk mengatur mekanisme Quality of Service (QoS) pada jaringan nirkabel. Melalui parameter tersebut, lalu lintas data seperti suara, video, background, dan best effort dapat diberikan prioritas yang berbeda sesuai kebutuhan. Dengan diterimanya Association Response ini, perangkat klien telah berhasil terhubung ke Access Point dan siap melakukan komunikasi data melalui jaringan Wi-Fi.
