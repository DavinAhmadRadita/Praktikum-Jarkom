# Modul 9 Web Server

Web server adalah perangkat lunak atau sistem yang bertugas menerima permintaan dari pengguna melalui internet atau jaringan, kemudian mengirimkan halaman web atau data yang diminta ke browser pengguna. Web server bekerja dengan menggunakan protokol HTTP atau HTTPS agar komunikasi antara pengguna dan website dapat berjalan dengan baik. Contoh web server yang sering digunakan adalah Apache HTTP Server, Nginx, dan Microsoft IIS. Fungsi utama web server adalah menyimpan, memproses, dan mengirimkan konten website seperti halaman HTML, gambar, video, maupun data aplikasi web kepada pengguna yang mengakses website tersebut.

## Langkah-Langkah membuat web sederhana

1. Membuat file python di vscode
2. lalu masukkan code berikut
```
from socket import *
import threading

def handle_client(connectionSocket):
    try:
        message = connectionSocket.recv(1024).decode()
        message = message[4:16]
        print(message)
        f = open(message[1:])
        outputData = f.read()
        connectionSocket.send(
            "HTTP/1.1 200 OK\r\n\r\n".encode()
        )

        connectionSocket.sendall(outputData.encode())

        connectionSocket.close()
    
    except IOError:
        connectionSocket.send(
            "HTTP/1.1 404 Not Found\r\n\r\n".encode()
        )

        connectionSocket.send(
            "<h1>404 Not found</h1>".encode()
        )

        connectionSocket.close()

serverSocket = socket(AF_INET, SOCK_STREAM)
serverSocket.bind(('', 6789))
serverSocket.listen(5)
print("[SYSTEM] server is running...")

while True:
    connectionSocket, addr = serverSocket.accept()

    thread = threading.Thread(
        target = handle_client,
        args = (connectionSocket,)
)
    thread.start()
```
3. buat file html di folder yang sama
4. isi code berikut pada file html
```
<html>
<head>
    <title>eak</title>
</head>
<body>
    <h1>awokawok berhasil</h1>
</body>
</html>
```
5. lalu jalankan file python nya terlebih dahulu
6. buka browser lalu ketik http://localhost:6789/index.html untuk menampilkan output dari file html

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/71a2af08-236b-4cbd-b8a3-186e409e1c77" />
