Nama : Davin Ahmad Radita

NIM : 103072400055

Kelas : IF-04-05

# Laporan Praktikum week 2 (HTTP)

# Tujuan praktikum
Agar Mahasiswa dapat menginvestigasi cara kerja protokol HTTP menggunakan Wireshark

# Basic HTTP GET/response interaction
1. Buka wireshark lalu pilih sesuai connection anda jika menggunakan wifi click wifi, lalu search http pada serach bar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/685792bc-7b45-4e41-bbfd-29239f69f783" />
2. lalu buka http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html pada browser anda
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5f62c8b3-f8c8-4d7b-bd8e-b01982c165ff" />
3. lalu akan muncul berbagai info packet pada wireshark seperti pada gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/14c3f2ea-4eaa-4060-8d6c-c9d46e5d7c2a" />

# Retrieving Long Documents
1. bersihkan cache browser terlebih dahulu
2. buka link http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html menggunakan browser anda lalu tampilan nya akan seperti pada gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6bcf6cef-d345-438c-b0c7-3e8c5e2636f1" />
3. lalu akan muncul berbagai info packet pada wireshark setelah membuka link tersebut
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0fe7a7fa-2ff4-410c-afa5-661264fc211d" />

# HTML Documents dengan Embedded Objects
1. bersihkan cache browser terlebih dahulu
2. buka link berikut menggunakan browser anda http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html, setelah di buka tampilan nya akan seperti pada gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8cbdca88-8075-4ef8-8655-5bd4dbbd3258" />
3. lalu akan muncul beberapa packet pada wireshark setelah membuka link tersebut
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/33da4725-f8e9-4ef7-9377-17c43b96114d" />

# HTTP Authentication
1. bersihkan cache browser terlebih dahulu
2. lalu buka link berikut menggunakan browser anda http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html, maka akan muncul seperti ini
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a8ff108a-cd24-42e4-84d8-b1b4c35cdab4" />
3. isi username dengan wireshark-students dan password dengan network, lalu tekan sign in. Setelah itu maka akan muncul tampilan seperti pada gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0cace2f5-d6ff-4f35-9489-5cee73b76549" />
4. lalu akan muncul beberapa info packet pada wireshark seperti pada gambar
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/03d864c4-68be-4721-816d-9a3cf1817c84" />
