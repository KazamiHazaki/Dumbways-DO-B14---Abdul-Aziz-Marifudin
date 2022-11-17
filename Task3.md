
pertama install NodeSource PPA  

```shell
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
```
![image](https://user-images.githubusercontent.com/56806850/202332468-0313d603-eea2-4caa-85b9-3535a431fb1b.png)

lalu install node source 

![image](https://user-images.githubusercontent.com/56806850/202332146-0faa0166-6862-41d6-a02f-d2e77d29d3a8.png)


setelah node source terinstall node js siap untuk di install

```shell
apt-get install -y nodejs
```

![image](https://user-images.githubusercontent.com/56806850/202332814-10a376ba-c04d-4ceb-9764-8ba752509336.png)


setelah install node js cek apakah sudah terinstall dengan 

```shell
node -v 
```
![image](https://user-images.githubusercontent.com/56806850/202333137-98caf8b3-4e6d-4771-ad88-aeebed6f65f7.png)


meluncurkan web app dengan node js

clone terlebih dahulu repo wayshub dengan command 

```shell
git clone https://github.com/dumbwaysdev/wayshub-frontend
```

setelah itu masuk ke directory `wayshub-frontend`

```shell
cd ~/wayshub-frontend
```

install menggunakan npm
![image](https://user-images.githubusercontent.com/56806850/202339623-08412346-bc09-4a6d-ac64-8fd6196195cb.png)


lalu jalankan 
```shell
npm run start
```

dan website wayshub-frontend telah berjalan menggunakan node.js
![image](https://user-images.githubusercontent.com/56806850/202340094-0dc7c736-343e-4c44-a7dd-9ef5f047257b.png)




