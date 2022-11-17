
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

![image](https://user-images.githubusercontent.com/56806850/202355989-c952a02e-a8d9-46a4-accc-04c100cf608c.png)

![image](https://user-images.githubusercontent.com/56806850/202355971-0909306a-f08f-4840-a90b-8e22faaec144.png)



dan website wayshub-frontend telah berjalan menggunakan node.js
![image](https://user-images.githubusercontent.com/56806850/202340094-0dc7c736-343e-4c44-a7dd-9ef5f047257b.png)


Install PM2

PM2 adalah proses manager node.js jdi kita bisa mengatur aplikasi node.js kita menggunakan PM2


```shell
npm install pm2 -g
```
![image](https://user-images.githubusercontent.com/56806850/202356496-c5cd4c5d-f386-49dc-9303-b2011b74d2a3.png)


cek sudah terinstall atau belum  dengan `pm2 -v`

![image](https://user-images.githubusercontent.com/56806850/202356663-3037955f-e18b-4835-be68-3ac27b832d60.png)


lalu kita jalankan dengan pm2
kita menggunakan `pm2 start "bash command'

maka untuk mendeploy ndoe js wayshub commandnya seperti ini 

```shell
pm2 start "npm run start" --name dumbways-web
```

![image](https://user-images.githubusercontent.com/56806850/202361753-41981119-08c4-408a-9408-f670b519f880.png)


mendeploy website menggunakan golang

pertama kita install terlebih dahulu package golang

download package terlebih dahulu

```shell
curl -OL https://golang.org/dl/go1.16.7.linux-amd64.tar.gz
```
![image](https://user-images.githubusercontent.com/56806850/202364574-d8fd501b-f974-469a-9e4a-313682f45660.png)

setelah itu kita extract ke folder `/usr/local`

```shell
sudo tar -C /usr/local -xvf go1.16.7.linux-amd64.tar.gz
```
![image](https://user-images.githubusercontent.com/56806850/202364899-cb475e27-abd0-4e47-879d-7b5da745ea14.png)

setelah extract selesai kita atur agar command go bisa di gunakan pada CLI kita dengan menambahkan path `/usr/local/go/bin` ke `~/.profile`

```shell
sudo nano ~/.profile 
```

lalu masukan `export PATH=$PATH:/usr/local/go/bin'  pada barisan bawah sendiri`

![image](https://user-images.githubusercontent.com/56806850/202366142-9d715f7b-2ed3-4870-ab8a-baa0d2a6d594.png)

setelah itu kita restart profile 
```shell
source ~/.profile
```
![image](https://user-images.githubusercontent.com/56806850/202366552-50d5b1b4-b44f-4219-a820-8b53cd8da2be.png)




setelah itu kita check instalasi kita menggunakan `go version`
![image](https://user-images.githubusercontent.com/56806850/202366640-68a98c42-4038-4013-b332-923a3daa0941.png)

Go language telah berhasil di install. langkah berikutnya kita settings golang agar bisa membuka website project kita.

selanjutnya kita membuat file yang akan di depol untuk tampilan websitenya

pertama kita masuk ke direktori go yang berada pada `/usr/local/go/bin`

buat direktori baru dan ubah akses direktory tersebut

```shell
sudo mkdir hello-world && cd hello-world
```

![image](https://user-images.githubusercontent.com/56806850/202369924-a6b6d744-8946-4c4b-bf24-d6b3e6de9dfc.png)

setelah itu kita ubah akses menjadi 777
![image](https://user-images.githubusercontent.com/56806850/202371654-262b5bcb-8748-4688-81e2-13589382f8a8.png)

![image](https://user-images.githubusercontent.com/56806850/202371672-d99bb74e-8c35-456c-9c5d-de53b592eadd.png)


lalu buat file go, pertama kita gunakan direktori sekarang sebagai module menggunakan command di bawah 

```shell 
go mod init mytask/hello-world
```
![image](https://user-images.githubusercontent.com/56806850/202371769-16549608-b75c-4775-a775-27c2a8493025.png)

lalu kita buat file go

```shell
nano hello.go
```

masukan command di bawah pada file hello.go

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}```

lalu kita jalankan golang yg sudah di buat dengan command 

```shell
go run hello.go
```

![image](https://user-images.githubusercontent.com/56806850/202487977-e7cac140-6974-4a59-b7bf-a0217024677e.png)

jika ingin di build aplikasi tersebut maka gunakan 

```shell
go build hello.go
```

maka setelah di build akan muncul file baru `hello`


![image](https://user-images.githubusercontent.com/56806850/202488583-82ffb075-e994-4747-acab-21a3b1ac00ac.png)


kita bisa langsung mengeksekusi file tersebut tanpa menggunakan `go run hello.go`

run menggunakan 

```shell
./hello
```

![image](https://user-images.githubusercontent.com/56806850/202489006-91f3e87c-b2ea-4589-9391-c0095ac1ffcd.png)




Install python3


pertama kita update terlebih dahulu 
![image](https://user-images.githubusercontent.com/56806850/202490902-79e18b6a-43ae-4386-ba18-a22ac6f56b61.png)

secara default python3 sudah terinstall pada ubuntu. maka kita bisa langsung saja check python3 dengan command berikut

```shell
python3 -V

```

![image](https://user-images.githubusercontent.com/56806850/202491685-9d7edb18-6815-4005-9f27-11377e8c79af.png)

lalu kita install pip package manager python3

```shell
sudop apt install python3-pip
```

setelah itu kita instal flask, flask adalah web framework yg ada pada python3, apa itu framework? framework adalah kerangka kerja yg sudah dibuat secara rapih dan mudah, sehingga membuat kinerja kita lebih efisien.

Install flask
```shell
pip install flask
````

![image](https://user-images.githubusercontent.com/56806850/202493078-9f9a56e9-c160-4ab3-9489-613517feab14.png)


setelah framewok flask terinstall mari kita buat file untuk websitenya

```shell
nano index.py
````
isi dengan konten berikut

```python3
from flask import Flask
app = Flask(__name__)
@app.route("/")
def helloworld():
    return "Abdul Aziz Marifudin"
if __name__ == "__main__":
    app.run()
```


![image](https://user-images.githubusercontent.com/56806850/202496402-14b84463-cfe4-40dc-8d41-cd5edae865be.png)



lalu kita jalankan menggunakan python

```shell
python3 index.py
```
lalu kita akan di beri halaman web dengan port 5000

![image](https://user-images.githubusercontent.com/56806850/202496768-d3f7619c-150b-42a8-8a19-cc20d47c2fac.png)

maka web dengan python3 berhasil di buat

![image](https://user-images.githubusercontent.com/56806850/202496588-1a2d11a2-369a-4702-950a-e25a1b928174.png)


