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


kemudian jalankan web app menggunakan PM2

sebelum di jalankan pada pm2 install web app tersebut menggunkan `npm -i`

![image](https://user-images.githubusercontent.com/56806850/203786214-57d725f6-0d55-40d8-beb6-742fb533d112.png)

setelah selesai test menggunakan `npm run start`


