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

ketika di jalankan maka script akan muncul seperti berikut

![image](https://user-images.githubusercontent.com/56806850/203571151-b8ba6991-06c6-470a-91cd-1648ce6e2051.png)

Teks manipulation "cat"

penggunaan cat 

cat [namafile]

pada command di bawah maka akan menunjukan isi teks dari sebuah file

```shell
cat file1
```
maka akan muncul teks yg ada di dalam file1

![image](https://user-images.githubusercontent.com/56806850/203573500-4e79cea8-7583-42b9-86ab-a6c5477c475b.png)



lalu bisa juga untuk membuat file baru

```shell
cat > file2
```
![image](https://user-images.githubusercontent.com/56806850/203574130-4154bf5a-7816-4cab-a951-05b76fead9c7.png)


setelah menjalankan perintah tersebut ketik teks yg ingin di isi pada file2. Jika sudah maka bisa di save dengan menggunkan CTRL+C.



```shell
cat file1 file2 > file3
```
![image](https://user-images.githubusercontent.com/56806850/203574343-6439bcb2-f0ff-4e6c-a41b-403dae5a1f9d.png)


penggunaan lain pada cat adalah untuk menggabungkan isi dari file1 dan file2 menjadi file baru

Teks Manipulation "Grep"

Teks manipulasi berikutnya `grep` digunakan untuk mencari text pada file yg sudah dibuat 

```shell
grep Dumbways file1
```
![image](https://user-images.githubusercontent.com/56806850/203575116-9207b464-ddb7-4898-96dc-15034d170301.png)

pada pencarian grep teks pencariannnya case-sensitive, jdi besar kecil teks yg dicari akan mempengaruhi hasilnya. penjelasan dari command di atas adalah mencari teks `Dumbways` pada file1

Menghitung kata dengan grep

```shell
grep -c Dumbways file1
```
![image](https://user-images.githubusercontent.com/56806850/203576263-d499fa50-f4e2-4e46-bdb6-9294fb8aae1c.png)


pada cli di atas terdapat `-c` fungsinya adalah menghitung teks. lalu kata yg ingin dicari `Dumbways` dan file yg dipilih merupakan `file1`, dan menghasilkan output satu, karena memang hanya terdapat 1 teks Dumbways saja.


Mencari teks pada seluruh folder

```shell
grep Dumbways *
```

![image](https://user-images.githubusercontent.com/56806850/203576702-9a72563d-0cf5-4418-8b4c-74adfe12a4a4.png)

setelah teks yg ingin di cari (`Dumbways`) terdapat symbol `*` digunakan untuk mencari keseluruhan pada semua file pada direktori itu.

Teks Manipulation "Echo"

Echo di gunakan untuk mencetak pesan pada teks atau output langsung pada terminal

Penggunaan Echo

```shell
echo "Hello Dumbways"
```
![image](https://user-images.githubusercontent.com/56806850/203577729-d474e36f-2f73-4a84-8e69-6bce2e4ba5a3.png)


langsung menampilkan output Dumbways pada terminal 


Untuk mencetak file menggunakan echo terdapat 2 cara 

```shell
echo "Abdul Aziz Marifudin" > file4
```

![image](https://user-images.githubusercontent.com/56806850/203596074-96319175-f2dd-403e-8a31-1ec9a0bcf5e6.png)


Cara pertama menggunakan operator lebih besar dari. fungsi dari ini pada CLI echo adalah mencetak file dengan menulis ulang teks yg ada pada file, semisal terdapat teks lain pada file tersebut maka teks yg seblumnya akan tertulis ulang.

```shell
echo "Dumbways.co.id" >> file4
```

![image](https://user-images.githubusercontent.com/56806850/203596196-13df405f-1490-44b0-93b0-df15bb20c826.png)


untuk cara kedua menggunakan `>>` pada symbol tersebut berfungsi untuk menambahkan text pada line baru di bawahnya.



Replace Text

Merubah text `Dumbways.co.id` pada seluruh file menjadi `bootcamp`

![image](https://user-images.githubusercontent.com/56806850/203597902-0bb87dda-c931-4b92-9fe7-07ec189f9679.png)

dengan menggunakan CLI `sed` maka kita bisa merubah text dengan sangat cepat

```shell 
sed 's/Dumbways.co.id/Bootcamp/g' file1 file2 file3 file4
```

![image](https://user-images.githubusercontent.com/56806850/203598474-46df722a-8183-4292-af3b-43b88a4d2ef7.png)


sed adalah stream editor digunakan untuk memanipulasi teks dengan cli. pada cli di atas `s` pertama adalah operasi substitusi lalu `/` adalah delimiter atau pemisah, diikuti dengan teks yg akan dirubah kemudian di pisah dengan `/` dan teks perubahan kemudian pada akhir terdapat option `g` perintah untuk mengganti teks pada keseluruhan line teks. lalu pilih file akan di rubah.

Challange 



  
