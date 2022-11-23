Perbedaan Shell dan Bash
Shell adala tampilan untuk pengguna berinteraksi dengan sistem operasi berbasis text
sedangkan Bash merupakan bahasa penerjemah yg berada di atas Shell.

Membuat Bash Script Update dan Upgrade Server
pertama buat scriptnya dengan command berikut 

```shell
nano script1.sh
```
pada command di atas perintah nano digunakan untuk membuat file baru setelah perintah di eksekusi maka akan muncul tampilan text editor seperti di bawah

![image](https://user-images.githubusercontent.com/56806850/203561826-51b47961-af5b-42e6-8c05-a35bfa698241.png)

di dalam text editor tersebut ketik perintah di bawah ini.

```shell
#!/bin/bash
sudo apt update && apt upgrade
```


fungsi perintah pada baris pertama `#!/bin/bash` adalah untuk mengindentifikasi simbol di awal `#!` disebut dengan shebang adalah awalan untuk membuat script bash di GNU, di ikuti dengan interpreter yang akan di gunakan
pada  script yang akan di buat menggunakan interpreter bash maka tulis lokasi direktori bash `/bin/bash`.

kemudian perintah update dan upgrade menggunakan `sudo apt update && apt upgrade` script tersebut merupakan 2 perintah yg di gabung menjadi 1 dengan operator logika `&&`, dimana jika kedua operand atau ekspresi operand true maka menghasilkan true.

![image](https://user-images.githubusercontent.com/56806850/203564857-371faebd-1020-46b7-be35-6e1024dbc5bf.png)
  
 
jika penulisan sudah sesuai tekan `ctrl + x` ketik `y` untuk menyimpan dan enter. Setelah itu jalankan script tersebut menggunakan S

```shell
bash script1.sh
```

setelah di jalankan maka akan di minta untuk memasukan password user. 

![image](https://user-images.githubusercontent.com/56806850/203565455-267f5413-fd19-4a0b-8301-ca67e6f130e2.png)

jika password benar maka akan lanjut ke proses update dan proses upgrade 

![image](https://user-images.githubusercontent.com/56806850/203565570-d3905fb7-ae0d-4aa7-b906-efcdb694b096.png)



Bash Script Open Port 22,80,443

membuat file script terlebih dahulu

```shell
nano script2.sh
```
lalu ketikan script seperti di bawah

![image](https://user-images.githubusercontent.com/56806850/203570561-e74f99a9-bfc3-43ae-9ef4-c8d903334fc9.png)


```shell
#!/bin/bash
sudo ufw allow 22;
sudo ufw allow 80;
sudo ufw allow 443;
sudo ufw enable ;
```


pada command di atas menggunakan pemisah delimiter atau `;` fungsi dari syhmbol tersebut adalah menjalankan perintah tidak peduli perintah yang pertama sukses atau tidak command kedua akan di eksekusi juga.
script di atas di awali dengan menggunakan command `sudo ` perintah tersebut akan membuat kita berubah langsung ke super user   ,
kemudian di ikuti dengan `ufw allow 22` untuk membuka port 22 pada firewall kita, dan seterusna membuka port 80 dan 443. setelah itu firewall di aktifkan menggunakan perintah `ufw enable`, Di akhiri dengan perintah `exit` untuk keluar dari mode super user

![image](https://user-images.githubusercontent.com/56806850/203569953-b96e8f67-686a-4999-9898-7c246efb1dbf.png)


