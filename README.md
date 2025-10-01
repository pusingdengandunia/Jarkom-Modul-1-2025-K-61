# SOAL 1 - 13

## Penjelasan

1. Membuat topologi jaringan sesuai yang diminta dalam soal
2. Memberikan sambungan internet ke node eru, dengan cara menyambungkan node eru ke NAT
3. Menghubungkan semua node satu sama lain
4. Menyambungkan semua client ke koneksi internet
<img width="711" height="598" alt="Image" src="https://github.com/user-attachments/assets/b72435d0-f418-43e1-bf76-172577e33378" />

5. Menginput semua script ke /root/.bashrc.
- Node Eru
```
apt update
apt install -y iptables
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.94.0.0/16
```
Untuk node client semuanya menggunakan `echo nameserver 192.168.122.1 > /etc/resolv.conf`

6. Buka Node Manwe

Download traffic serta jalankan di node Manwe

Start Capture di wireshark antara switch1 dan eru

lakukan display filter 'ip.addr == ip manwe '
<img width="1920" height="1020" alt="Image" src="https://github.com/user-attachments/assets/670f82e3-a19c-4d36-8893-312fbeb1b590" />


7. Buka Server Eru

buat direktori chroot dan subfolder writable

chown/chmod: root owns chroot root directory

buat group ftpusers

buat subfolder yang writable untuk user ainur

buat user ainur chrooted ke /srv/ftp/shared (home)

buat user melkor dengan home /home/melkor

buat serta simpan config vsftpd
```
ps aux | grep vsftpd (cek vsftpd aktif ngga)
killall vsftpd
vsftpd /etc/vsftpd.conf &
ps aux | grep vsftpd (cek jika aktif maka udh ganti config)
```

- UJI DI NODE CLIENT (Ulmo)
lakukan upload dengan cara put, dan lakukan download dengan cara get

8. Lakukan koneksi dari node ulmo ke FTP server (Lakukan urut mulai dari nomer 7)

download file nya dulu

lakukan login ftp dengan user ainur

upload dengan cara put
<img width="1920" height="1020" alt="Image" src="https://github.com/user-attachments/assets/09655125-24c7-4bc8-8a23-70643e1ba397" />

9. Masuk ke Eru (Lakukan urut mulai dari nomer 7)

download file kitab

pindahkan file kitab ke direktori share data

lakukan wireshark capture antara switch1 dan manwe
### Masuk ke Manwe

Login dengan ainur

Masuk ke direktori data dan lakukan download txt file
<img width="1856" height="337" alt="Image" src="https://github.com/user-attachments/assets/477bcc62-87ab-4c53-aa82-311fa3eb09d6" />
### Masuk ke Eru

Lakukan perubahan izin untuk ainur
```
cd /srv/ftp/shared/data
chown root:root "kitab_penciptaan.txt"
chmod 644 "kitab_penciptaan.txt"
```
### Masuk ke Manwe

Lakukan put dengan user ainur

Cek apakah gagal
<img width="1727" height="155" alt="Image" src="https://github.com/user-attachments/assets/44d3bef2-9247-4144-ae6b-9b8ff907b3bb" />

10. Masuk ke Melkor

buat file detect ping sebelum serangan dan sesudah serangan
<img width="1896" height="381" alt="Image" src="https://github.com/user-attachments/assets/10f96304-835b-49f5-84e8-5203576a5929" />

11. Masuk ke Melkor untuk buat id baru serta capture eru login dengan id baru
<img width="1920" height="1020" alt="Image" src="https://github.com/user-attachments/assets/ab230adc-4555-40d0-be41-61c584c32c2c" />

12. Masuk ke Eru untuk melakukan scan port 21, 80, 666

13. Lakukan koneksi SSH antara Varda dan Eru
<img width="1920" height="1020" alt="Image" src="https://github.com/user-attachments/assets/61c03e9a-77c9-4f0f-81cc-595d46f7ba86" />
