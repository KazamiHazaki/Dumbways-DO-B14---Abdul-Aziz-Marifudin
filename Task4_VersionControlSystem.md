
Apa itu GIT?
Git adalah version control system. yg di maksud version control system adalah aplikasi  untuk mengontrol setiap perubahan yg ada pada aplikasi, dari tahap pembuatan aplikasi hingga update aplikasi ketika sudah di rilis ke publik



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


dan kita coba koneksi dengan SSH pada host windows

![image](https://user-images.githubusercontent.com/56806850/202521893-fe2de2a5-88d2-4e82-85d5-9deca2b51672.png)

SSH berhasil terhubung dengan ubuntu server pada VM

![image](https://user-images.githubusercontent.com/56806850/202522011-bc4b649c-2bb8-4a4b-a938-e68e109f22c6.png)


Check hostname VM

![image](https://user-images.githubusercontent.com/56806850/202593922-ddecddce-b9f2-4ac0-b03f-f7498e2d7c3d.png)

Setelah itu kita hubungkan ke server 

![image](https://user-images.githubusercontent.com/56806850/202594057-0f88f9a1-812b-42f5-87a1-be5e9e90d1d9.png)

setelah itu masukann password

![image](https://user-images.githubusercontent.com/56806850/202594111-a5bdea5f-40d5-4ff2-8fe4-c14bc0d36f1a.png)

cek kembali menggunakan hsotname, dan SSH sudah terhubung 

![image](https://user-images.githubusercontent.com/56806850/202594166-44248310-f10e-4fc1-b4f8-0497975c95c7.png)



Menghubungkan Github 

masukan username github 
```shell
git config --global user.name "KazamiHazaki"
```

![image](https://user-images.githubusercontent.com/56806850/202594386-3f70426a-e348-46f9-88be-83f1408d788a.png)


masukan email github

```shel
git config --global user.emal "alluka.zoldyck999@gmail.com"
```

![image](https://user-images.githubusercontent.com/56806850/202594452-e53a7bf9-7129-4a1a-a0a9-2a1955677046.png)

lalu cek configurasi yg baru saja di buat dengan 

```shell
git config --list
```
![image](https://user-images.githubusercontent.com/56806850/202594818-e219a4dc-f5fb-475f-982a-4f816ad2aa82.png)

lalu kita buat SSH key

pertama kita buat direktori untuk mencimpan kunci tersebut 

```shell
mkdir .key && cd .key
```

![image](https://user-images.githubusercontent.com/56806850/202595637-13549137-66f5-4a2a-a01c-0494d8426808.png)

lalu kita buat kunci SSH 

```shell
ssh-keygen
```

masukan kunci pada ssh jika ingin menggunakannya

![image](https://user-images.githubusercontent.com/56806850/202595887-e5a4ce40-4482-4076-8f10-678965c3f052.png)


lalu kita cek kunci yg sudah kita buat di folder `/root/.ssh/`

![image](https://user-images.githubusercontent.com/56806850/202596027-4f6b1a4e-1143-4c24-b054-3f8af9af0046.png)

ssh sudah dibuat lalu kita masukin kunci tersebut ke dalam akun github kita
di halaman https://github.com/settings/keys

pertama kita copy terlebih dahulu kunci public yg sudah dibuat

```shell
cat /root/.ssh/id_rsa.pub
```

lalu kita copy kunci tersebut 

![image](https://user-images.githubusercontent.com/56806850/202596565-97a0d240-4b79-421f-84b9-d431f27146af.png)


ke dalam link github di atas

![image](https://user-images.githubusercontent.com/56806850/202596750-8ddf3352-6770-466f-bd34-e8ab58cb8bcb.png)

setelah di paste tekan Add SSH key

setelah menambahkan kunci ke akun github lalu kita check koneksi SSH kita 

```shell
ssh -T git@github.com
```

![image](https://user-images.githubusercontent.com/56806850/202596952-c59881bc-3e58-4537-a3f5-9144ebcbf9e5.png)

jika kalian mengisi passpharse/password saat membuat keygen maka anda akan di tanyakan untuk mengisi password tersebut.jika benar maka koneksi akan terhubung dengan akun github `Hi KazamiHazaki! You've successfully authenticated, but GitHub does not provide shell access.
`


Membuat Branch

setelah terhubung dengan Github pada ssh kita maka yg kita buat terlebih dahulu ada lah membuat repository

```shell
git init task-dumbways
```

![image](https://user-images.githubusercontent.com/56806850/202597387-5a767db7-ec09-4ffd-9e91-217b9d141836.png)

direktori sudah di buat, kita coba buat file dan upload ke repository

```shell
echo "abdul aziz" > test.txt
```

![image](https://user-images.githubusercontent.com/56806850/202597736-4fa2706d-022f-4cad-9aa8-6f5261e2a47c.png)

file sudah di buat maka kita cek perubahan pada git, menggunakan command 

```shell
git status 
```

![image](https://user-images.githubusercontent.com/56806850/202597809-9a8f2bfd-2e56-467f-b696-599f03f98484.png)


Jika ada tulisan seperti di atas maka kita bisa mengirimkannya pada repository kita.

```shell
git add test.txt
```
![image](https://user-images.githubusercontent.com/56806850/202598029-50bc67a6-258d-475f-9605-a6845991f40f.png)

maka file test.txt bisa kita kirimkan

pertama kita gunakan commit untuk mendeskripsikan apa yg sudah kita lakukan perubahan pada repository kita

```shell 
git commit -m "upload test.txt"
```
![image](https://user-images.githubusercontent.com/56806850/202598405-aedbd893-6314-4fcc-b514-1d7a2fd902a7.png)

perubahan sudah di lakukan dan kita  kirim ke github seluruh repository lokal pada github


sebelum itu pastikan sudah membuat repository di web github. lalu kita remote repo tersebut ke lokal git kita

```shell
git remote add origin https://github.com/KazamiHazaki/test.git
```
![image](https://user-images.githubusercontent.com/56806850/202599182-7b688888-53b8-459c-be1f-9611f16ee7df.png)


lalu cek apakah sudah terhubung atau belum

```shell
git remote -v
```


![image](https://user-images.githubusercontent.com/56806850/202599283-e29acd5c-48b3-43f7-b659-535a752f4be0.png)

setelah itu kita upload file test.txt kita dari lokal ke online database github

```shell
git push -u origin main
```

