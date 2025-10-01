# SOAL 1 - 13

## Penjelasan

1. Membuat topologi jaringan sesuai yang diminta dalam soal
2. Memberikan sambungan internet ke node eru, dengan cara menyambungkan node eru ke NAT
3. Menghubungkan semua node satu sama lain
4. Menyambungkan semua client ke koneksi internet
<img width="711" height="598" alt="Image" src="https://github.com/user-attachments/assets/b72435d0-f418-43e1-bf76-172577e33378" />

5. Menginput semua script ke /root/.bashrc.

> Node Eru
'''
apt update
apt install -y iptables
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.94.0.0/16
'''
Untuk node client semuanya menggunakan 'echo nameserver 192.168.122.1 > /etc/resolv.conf'

6. Buka Node Manwe
Download traffic serta jalankan di node Manwe
Start Capture di wireshark antara switch1 dan eru
lakukan display filter 'ip.addr == ip manwe '
