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


```shell
#!/bin/bash
sudo apt update -y;
sudo apt upgrade -y;

``` 
