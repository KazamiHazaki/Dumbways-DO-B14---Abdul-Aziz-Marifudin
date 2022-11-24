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


         
