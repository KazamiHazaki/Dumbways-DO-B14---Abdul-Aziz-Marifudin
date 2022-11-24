Mempersiapkan Nginx Server dan Node Js Pada 2 vm berbeda

Menginstall Nginx pada VM 

pada installasi nginx jalankan  script di bawah ini untuk memudahkan proses installasi.

![image](https://user-images.githubusercontent.com/56806850/203778999-4cd5f5e3-139b-4e05-b94a-ee6646e3ae37.png)

```shell
#!/bin/bash
sudo apt update -y;
sudo apt upgrade -y;
sudo apt install nginx -y;
nginx -v;
sudo systemctl status nginx;
``` 

jalankan menggunakan 

```shell
bash nginx_auto.sh
```


lalu ketika script selesai di jalankan, nginx bisa di cek melalui IP VM
![image](https://user-images.githubusercontent.com/56806850/203770122-489cbf64-5424-4d66-b1c0-ba8c9372f9d5.png)




Mempersiakan Node Js front end Web app


![image](https://user-images.githubusercontent.com/56806850/203780367-b51c795d-97cc-41bf-8b45-9cf371446bb0.png)


```shell
#!/bin/bash
sudo apt update -y;
sudo apt upgrade -y;
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh;
sudo bash nodesource_setup.sh;
apt install nodejs -y;

``` 

lalu jalankan script dan tunggu proses installasi.

![image](https://user-images.githubusercontent.com/56806850/203782940-0cd818ff-ff36-4be4-b427-4ff26c6bc57e.png)

setelah installasi selesai check node js dengan `node -V`

kemudian  download frontend websitenya.

![image](https://user-images.githubusercontent.com/56806850/203783770-488e6653-088b-4573-a040-52e13fff964d.png)


```shell
git clone https://github.com/dumbwaysdev/wayshub-frontend.git
```
install PM2 
```shell
sudo npm install pm2 -g
```
![image](https://user-images.githubusercontent.com/56806850/203784992-96022035-4eb9-43f1-853c-013ca92c5c8d.png)

setelah installasi selesai lakan lagi pengecekan pm2 dengan `pm2 -v`

![image](https://user-images.githubusercontent.com/56806850/203785206-1461f69b-ed11-4674-8ed9-eef21e966371.png)

sebelum menjalankan applikasi buka terlebih dahulu port firewall server 

![image](https://user-images.githubusercontent.com/56806850/203792511-0778a8cb-4823-4abe-aee7-69e4a0ab72e6.png)


```shell
sudo ufw allow 3000
```

kemudian jalankan web app menggunakan PM2

sebelum di jalankan pada pm2 install web app tersebut menggunkan `npm -i`

![image](https://user-images.githubusercontent.com/56806850/203786214-57d725f6-0d55-40d8-beb6-742fb533d112.png)

setelah selesai test menggunakan `npm run start`

lalu jika berhasil maka akan muncul seperti berikut 

![image](https://user-images.githubusercontent.com/56806850/203792618-daa6787d-955f-41c7-885b-4e216f495c62.png)

dan web app sudah bisa di akses melalui web browser dengan port 3000.

lalu kita gunakan PM2 agar web app kita bisa berjalan di background sehingga ketika kita menutup terminal web app masih bisa di akses selama vps masih menyala.

```shell
pm2 start "npm run start" --name dumbways-web
```
![image](https://user-images.githubusercontent.com/56806850/203795165-975421ce-5272-4d0f-b333-37fbce593657.png)

jika status online maka web app sudah berjalan di background.


lalu kita menghubungkan 2 web server dengan menggunakan reverse proxy dari vm2 yang berisi web server nginx dan web app wayshub-frontend. 

pada latihan ini vm terbagi menjadi 2 yaitu : 

Ubuntu1  : 
- Sebagai Web app
- IP 192.168.1.125

Ubuntu2 :
- Sebagai web server nginx
- IP 192.168.1.118


jadi untuk konsep reverse proxy adalah seperti ini gambarannya 

![image](https://user-images.githubusercontent.com/56806850/203798387-a95ad0aa-bab0-4abd-8a8c-5f98cb2bbaf1.png)


Ketika client ingin mengakses website wayshub client tidak langsung membuka dari IP Server Node JS dengan IP `192.168.1.125` tetapi ketika client membuka domain wayshub semisal domainnya adalah wayshub.co.id IP pada domain tersebut adalah IP pada server nginx dengan IP 192.168.1.118.


alur nya adalah 

- Client membuka wayshub.co.id (IP 192.168.1.118)
- Di terima Server proxy (nginx IP 192.168.1.118)
- lalu server proxy mengarahkan pada Server original yaitu 192.168.1.125
- kemudian server 192.168.1.125 mengirim kembali permintaan client ke pada Server Proxy Nginx
- Nginx memberikan request client tampilan website wayshub.co.id

pertama kita lakukan pengaturna reverse proxy pada server nginx

masuk ke folder nginx 

```shell
sudo cd /etc/nginx
```

lalu buat folder baru 

```shell
sudo mkdir wayshub
```
kemudian masuk ke direktori tersebut dan  buat  file conf baru dengan nama `wayshub_proxy.conf`

```shell
sudo nano wayshub_proxy.conf
```
dan isi pada file conf 

```shell
server { 
    server_name mydomain.xyz; 
  
    location / { 
             proxy_pass http://127.0.0.1:3000;
    }
}
```
dan tambahkan folder yang sudah di buat pada file configurasi nginx
buka file config nginx

```shell
sudo nano nginx.conf
```
dan tambahkan di bawah `include /etc/nginx/sites-enabled/*;` setelah masuk ke text editor nano tekan `ctrl + w`
cari teks `include /etc/nginx/sites-enabled/*;` tuliskan direktori wayshub yg sudah di buat.

![image](https://user-images.githubusercontent.com/56806850/203805639-32fdb79c-1dfe-4669-9968-4ccd8333e609.png)


kemudai test configurasi yg sudah di tambahkan direktori baru dengan 

```shell
sudo nginx -t
```

![image](https://user-images.githubusercontent.com/56806850/203805942-f6d61f75-473c-4bf0-8abb-8757ac611a9a.png)


kemudian restart nginx untuk mengaplikasikan perubahan.

```shell
sudo systemctl restart nginx
```

lalu tambahkan domain yg di buat pada conf baru kita
edit pada file hosts

```shell
sudo nano /etc/hosts
```
![image](https://user-images.githubusercontent.com/56806850/203806903-8f500063-3607-4fa5-98da-cc4fef782ec8.png)

setelah itu masukan domain yg di atur pada .conf sebelumnya pada web client 


![image](https://user-images.githubusercontent.com/56806850/203807823-65fc70bc-afa3-45bf-9f17-0b94f7096042.png)

lalu kita coba domain tersebut di akses melalui web browser.


![image](https://user-images.githubusercontent.com/56806850/203808053-7c44ed07-a42d-46fd-bb89-7f747aff11ab.png)

jika sudah muncul seperti ini maka domain sudah bisa di akses melalui `webaziz.xyz` pada client 


maka setelah itu kita rubah pada conf nginx proxy pass di arahkan ke  web nodeJS.

![image](https://user-images.githubusercontent.com/56806850/203808841-fbfbfa8a-93ae-49db-a702-453ac3692518.png)

nah lalu kita bisa langsung bisa mengakses web server nodeJS

![image](https://user-images.githubusercontent.com/56806850/203809009-be215d54-4017-4186-93c3-6e6d88d29c37.png)



lalu kita kita lihat IP yg digunakan pada  domain.xyz menggunakan ping pada client

![image](https://user-images.githubusercontent.com/56806850/203809478-ff28da05-c8ed-461e-a1e3-d3124e2bfab6.png)

disitu menunjukan IP yg di gunakan webaziz.xyz adalah 192.168.1.118 dimana IP tersebut adalah IP server nginx

![image](https://user-images.githubusercontent.com/56806850/203810407-8e3af9c2-1981-4a63-a0ef-d422bd955483.png)

jadi karena .conf nginx sudah di rubah maka ketika client mengakses halaman web webaziz.xyz nginx akan mengarahkan langsung ke server nodeJS yaitu `192.168.1.125:3000`



Untuk membuat load balancing tambahkan Upstream domaain pada confg nginx sebelumnya

```shell
upstream domain {
    server 192.168.1.118:3000;
    server 192.168.1.125:3000;
}
```


