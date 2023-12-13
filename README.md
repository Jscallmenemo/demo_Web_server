# demo_Web_server
Installing and Configuration My Simple Web Server

# Latar Belakang
sebagai tugas final project mata kuliah OS Server dan System Admin, saya akan membuat layanan Web Server.

# Bahan yang harus dipersiapkan untuk membuat Web Server
1. Virtual Machine
2. Iso Ubuntu Server - Ubuntu Server 22
3. Apache2
4. WinSCP
   
# Update Progress
1. Menentukan Jenis layanan yg ingin dibuat
2. Instalasi Ubuntu Server pada Virtual Machine
3. Membuat Akun Github
4. Mulai mengisi repository Github

## Install Apache2
Apache adalah software web server gratis dan open source yang memungkinkan user mengupload website di internet.
Langkah 1 : Update Repository Ubuntu Server
```bash
sudo apt update
```

Langkah 2 : Install Apache2
```bash
apt-get install apache2 -y
```

langkah 3 : Setting Firewall
```bash
sudo ufw app list
```
```bash
Output
Available applications:
  Apache
  Apache Full
  Apache Secure
  OpenSSH
```
Disarankan untuk mengaktifkan profil yang paling ketat yang masih akan mengizinkan lalu lintas yang telah dikonfigurasikan.
```bash
sudo afw allow 'Apache'
```
Verifikasi perubahan status
```bash
sudo ufw status
```
Output akan mengeluarkan daftar lalu lintas HTTP yang diizinkan
```bash
Output
Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere                  
Apache                     ALLOW       Anywhere                
OpenSSH (v6)               ALLOW       Anywhere (v6)             
Apache (v6)                ALLOW       Anywhere (v6)
```

Langkah 4 : Memeriksa Web Server 
Periksa web server apakah sudah berjalan atau tidak
```bash
sudo systemctl status apache2
```
```bash
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Mon 2023-12-11 13:05:15 UTC; 1 day 11h ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 4560 ExecReload=/usr/sbin/apachectl graceful (code=exited, status=0/SUCCESS)
   Main PID: 2677 (apache2)
      Tasks: 55 (limit: 4515)
     Memory: 5.7M
        CPU: 1.790s
     CGroup: /system.slice/apache2.service
             ├─2677 /usr/sbin/apache2 -k start
             ├─4636 /usr/sbin/apache2 -k start
             └─4637 /usr/sbin/apache2 -k start
```



