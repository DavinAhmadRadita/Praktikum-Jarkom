# MODUL 13 ARP

ARP (Address Resolution Protocol) adalah protokol jaringan yang digunakan untuk menerjemahkan atau mencocokkan alamat IP Address menjadi MAC Address pada jaringan lokal (LAN). ARP bekerja ketika sebuah perangkat ingin mengirim data ke perangkat lain dalam jaringan yang sama tetapi hanya mengetahui alamat IP tujuan. Dengan menggunakan ARP, perangkat dapat mencari dan memperoleh MAC Address dari alamat IP tersebut sehingga data dapat dikirim ke perangkat yang tepat melalui jaringan. ARP merupakan protokol penting dalam komunikasi jaringan karena perangkat membutuhkan MAC Address tujuan untuk melakukan pengiriman data pada layer data link.

## Cara Kerja ARP

1. Perangkat sumber mengetahui alamat IP tujuan, tetapi belum mengetahui MAC Address tujuan.
2. Perangkat sumber memeriksa ARP Cache untuk melihat apakah MAC Address tujuan sudah tersimpan.
3. Jika tidak ditemukan, perangkat mengirim ARP Request secara broadcast ke seluruh perangkat dalam jaringan lokal.
4. ARP Request berisi pertanyaan mengenai siapa pemilik alamat IP yang dituju.
5. Perangkat yang memiliki alamat IP tersebut akan mengirim ARP Reply yang berisi MAC Address miliknya.
6. Perangkat sumber menerima ARP Reply dan menyimpan pasangan IP Address – MAC Address ke dalam ARP Cache.
7. Setelah MAC Address tujuan diketahui, perangkat sumber dapat mengirimkan data ke perangkat tujuan melalui jaringan.
8. Untuk komunikasi berikutnya, perangkat dapat menggunakan informasi yang tersimpan di ARP Cache tanpa perlu mengirim ARP Request lagi selama data tersebut masih valid.

## Langkah-Langkah

1. Buka cmd lalu run as administrator, setekah itu jalankan perintah arp -d * pada cmd untuk menghapus semua dapat yang tersimpan pada ARP Cache
<img width="270" height="52" alt="image" src="https://github.com/user-attachments/assets/79e52d84-8056-49de-9c3b-6450b58cbf1e" />

2. Buka wireshark lalu pilih Analyze → Enabled Protocols → IPv4
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d4ba97a5-22d9-407f-8936-ac4a441146f9" />

3. Start capture wireshark
4. Setelah start capture buka website "http://gaia.cs.umass.edu/wireshark-labs/HTTP-ethereal-lab-file3.html"
5. Setelah membuka website tersbeut stop capture pada wireshark
6. Ketik "arp" pada seach bar
<img width="1918" height="468" alt="image" src="https://github.com/user-attachments/assets/a06e364f-9258-4138-8224-4c18b36f0cda" />

7. Pilih salah satu packet untuk di analisis
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/45ad4c67-aaee-4d62-9121-81f24999137c" />

Berdasarkan hasil capture Wireshark, paket yang dipilih merupakan ARP Request (Opcode = request/1). Perangkat dengan IP Address 10.144.53.2 dan MAC Address f6:54:f7:de:c3:69 mengirimkan permintaan untuk mengetahui MAC Address dari perangkat yang memiliki IP Address 10.144.53.204. Karena alamat MAC tujuan belum diketahui, Target MAC Address masih bernilai 00:00:00:00:00:00. Pada kolom informasi terlihat pesan "Who has 10.144.53.204? Tell 10.144.53.2", yang berarti perangkat 10.144.53.2 sedang menanyakan siapa pemilik alamat IP 10.144.53.204. Setelah permintaan tersebut dikirim, perangkat dengan IP 10.144.53.204 memberikan balasan ARP yang menyatakan "10.144.53.204 is at b8:1e:a4:96:65:57", sehingga alamat IP berhasil dipetakan ke MAC Address yang sesuai. Dari hasil tersebut dapat disimpulkan bahwa protokol ARP digunakan untuk menerjemahkan atau mencocokkan alamat IP Address menjadi MAC Address agar komunikasi antar perangkat dalam jaringan lokal dapat berlangsung dengan benar.
