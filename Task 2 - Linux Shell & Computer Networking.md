Pertama kita hubungkan ke Ubuntu server kita terlebih dahulu lalu login dengan akun yg sudah dibuat.

![image](https://user-images.githubusercontent.com/56806850/201913268-e9edb988-6e7c-4ec4-b9b2-86737f868e83.png)

kita lakukann update ubuntu terlebih dahulu.

![image](https://user-images.githubusercontent.com/56806850/201913459-2b7560f2-90e0-4013-a6d0-4881ef193691.png)


setelah update selesai 

kita install package apache2 

```shell
sudo apt install apache2
```

![image](https://user-images.githubusercontent.com/56806850/202314524-6ce58bee-fa5d-4606-92a2-a2cb26845f0b.png)


setelah proses installasi selesai, pastikan apache sudah terinstall dengan commannd

```shell
apache2 -v
```
![image](https://user-images.githubusercontent.com/56806850/202314755-0218faaa-ef6a-4b65-a8aa-cb012d78145b.png)

selanjutnya kita check firewall kita agar web server bisa di akses 

```shell
sudo ufw status
```

![image](https://user-images.githubusercontent.com/56806850/202314944-d9bd17f0-52b1-4d64-b3b2-325c7cb98e03.png)

untuk server saya yang sudah aktive adalah SSH, web server apache2 belum aktif. mari kita aktifkan terlebih dahulu

```shell
ufw allow 'Apache Full'
```
![image](https://user-images.githubusercontent.com/56806850/202315202-b512924e-151d-451b-9976-f1371bcfc4b1.png)

pada gambar di atas port firewall sudah di buka, kita check kembali dengan ufw status

![image](https://user-images.githubusercontent.com/56806850/202315279-f7057065-8295-4d3d-83e5-23da657b9895.png)

jika sudah seperti gambar di atas port firewall apache sudah terbuka dan dapat di akses. Setelah pengaturan awal kita check status apache aktif atau tidak

```shell
sudo systemctl status apache2
```

![image](https://user-images.githubusercontent.com/56806850/202315499-7f454513-0b7d-4b71-af0f-7ef090e91c1f.png)

jika seperti gambar di atas maka, installasi apache2 berhasil dan sudah berjalan. lalu kita check apache pada web browser kita. kita check terlebih dahulu IP server kita 

```shell
hostname -I
```

setelah itu kita akses melalui browser windows

![image](https://user-images.githubusercontent.com/56806850/202315975-4d098c5d-12b1-4678-ab84-7847b79e4fe2.png)

jika sudah muncul halaman seperti di atas maka, apache2 sukses di install.

Jika ingin mengubah tampilan apache2 menjadi sesuai keinginan kita, maka kita harus merubah file yang ada pada `/var/www/html` 

