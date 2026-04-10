# Modul 5 UDP
UDP (User Datagram Protocol) adalah salah satu protokol komunikasi dalam jaringan komputer yang digunakan untuk mengirim data antar perangkat dengan cara yang cepat dan sederhana. Berbeda dengan protokol lain seperti TCP, UDP tidak melakukan pengecekan apakah data yang dikirim berhasil sampai atau tidak, sehingga tidak ada proses konfirmasi, pengurutan, atau perbaikan data yang hilang.

## Langkah - Langkah

1. Download file dari link berikut http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip
2. extrack file yang sudah di download dari link tersebut
<img width="758" height="93" alt="image" src="https://github.com/user-attachments/assets/ef0dbe1d-d226-4bb3-892a-56bddf5787db" />

3. Setelah di extract pilih file bernama "http-ethereal-trace-5" dan buka menggunakan wireshark
<img width="750" height="39" alt="image" src="https://github.com/user-attachments/assets/8a689ce5-c6b6-4d8b-a52f-0e01dbcb970d" />

4. Setelah membuka file nya menggunakan wireshark ketik udp pada kolom filter agar terfilter.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c85daad8-6744-47a0-92ee-6d961c1bd0d6" />

## Pertanyaan

## Jawaban

1. Pada paket UDP yang dipilih dari hasil trace, terdapat 4 field pada header UDP, yaitu Source Port, Destination Port, Length, dan Checksum.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e7741b0a-a2af-4f4c-a464-ec9f544334b5" />

2. Pada header UDP, setiap field memiliki panjang tetap. Source Port memiliki panjang 2 byte, Destination Port memiliki panjang 2 byte, Length memiliki panjang 2 byte, dan Checksum memiliki panjang 2 byte, sehingga total panjang header UDP adalah 8 byte.

3. Nilai yang tertera pada field Length pada header UDP menyatakan panjang total paket UDP, yaitu gabungan antara header UDP dan data (payload) dalam satuan byte. Verifikasi dari paket pada trace menunjukkan bahwa nilai Length = 58 byte, di mana 8 byte merupakan panjang header UDP dan sisanya 50 byte adalah data (payload), sehingga sesuai dengan informasi yang ditampilkan (UDP payload (50 bytes)).


