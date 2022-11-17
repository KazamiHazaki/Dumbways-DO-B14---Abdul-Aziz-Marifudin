
Setelah login ke VM
masuk ke direktori dan cek file yg ada di direktori tersebut

check IP kita terlebih dahulu

```shell
hostname -I
```
![image](https://user-images.githubusercontent.com/56806850/202520770-9e70969b-407e-420d-9cdb-c08105245338.png)


```shell
cd /etc/netplan
ls
```
![image](https://user-images.githubusercontent.com/56806850/202516666-57c70d14-130f-47ee-b741-03f6da3face4.png)

kemudian kita edit file tersebut

```shell
nano 00-installer-config.yaml
```
maka akan muncul isi dari yaml seperti berikut
![image](https://user-images.githubusercontent.com/56806850/202520907-30dc7484-4205-43cf-bc64-c40970a5f59b.png)

kita rubah IP 192.168.1.233 ke ip yg kita mau saya rubah ke 111
![image](https://user-images.githubusercontent.com/56806850/202521081-a51c9d64-d626-4fa3-b23c-277e21111918.png)

lalu kita apply ke system IP kita menggunakan 

```shell
netplan apply
```
lalu kita cek menggunnakan ping
![image](https://user-images.githubusercontent.com/56806850/202521417-02833047-a4b8-448e-a4e0-6930240369a1.png)

dan cek IP kita sudah berubah atau belum menggunakan `Hostname -I`

![image](https://user-images.githubusercontent.com/56806850/202521529-3a63eb71-f0f6-42a9-8db8-a02236fd7099.png)



