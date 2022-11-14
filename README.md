# Dumbways-DO-B14---Abdul-Aziz-Marifudin
Dumbways Devops Task 1 - Abdul Aziz marifudin

Apa itu DevOps?
Devops adalah gabungann dari Development dan IT Operation, Dimana penghubung antara divisi Developer dan IT Operation.Dimana merupakan kombinasi dari kultur,praktik, dan tools. yang membuat kolaborasi dan efisiensi dalam kerjasama team antara Developer dan IT Operation

DevOps LifeCycle
Apa yg di makusd dengan DevOps Lifecycle? Merupakan tahapan-tahapan ketika mengembangkan sebuah aplikasi.

Tahapan apa saja pada DevOps LifeCycle?
Code >> Build >> Test >> Release >> Deploy
 
![image](https://user-images.githubusercontent.com/56806850/201646351-fc77500f-7186-49d6-802f-7d59d7de7440.png)

Code 
Pada tahapan ini Developer menulis dan mengembangkan Code aplikasi dalam berbagai bahasa.

Build 
setelah kode aman dan siap di gunakan lalu kode tersebut di eksekusi melalui proses build, atau di rubah dari bentuk kode menjadi aplikasi yang bisa di gunakan

Test
Pada tahapan ini aplikasi di uji coba (Test).Di uji fungsional,kinerja,desain,keamanan

Release
Lalu setelah dilakukan pengujian masuk pada tahap perilisan. dimana dikemas dengan nomor versi perilisan. nomor versi perilisan menunjukan suatu perubahan pada aplikasi di tiap nomor versi periisan.

Deploy
Masuk ke tahap akhir yaitu Deploy aplikasi ke environment/lingkunan ke server hingga siap di gunakan. meski masih dalam tahap test, staging (tempat di mana masih banyak perubahan), alpha,beta, atau production


Instalasi Ubuntu Server 20.04 LTS

Pada instalasi Ubuntu Server ini saya akan menggunakan aplikasi VM.
Yaitu Virtual Box Versi 6.1.40 yang bisa di download secara Free


Bahan Instalasi
 
Virutal Box 6.1.40 - Link Download https://www.virtualbox.org/wiki/Download_Old_Builds_6_1 


Ubuntu Server 20.04.1 - Link Download https://ubuntu.com/download/server

Tahap 1 - Menyiapkan Virtual Box
![image](https://user-images.githubusercontent.com/56806850/201662603-d66d8994-f8e3-405b-88eb-2ec664727169.png)
Buka Aplikasi Virtual Box yang sudah di install lalu tekan tombol New seperti gambar di atas.

![image](https://user-images.githubusercontent.com/56806850/201663041-4090ee03-0705-44ea-822c-038a6006cc66.png)
Beri nama Virtual machine, saya memberi nama Ubuntu 20.04 LTS. Untuk lokasi penyimpanan VM saya biarkann default. Pilih type Linux lalu versinya Ubuntu 64 Bit

![image](https://user-images.githubusercontent.com/56806850/201663552-435bad35-7e60-49ea-b8c0-3ba14b12092b.png)
Buat ukuran Virtual Memmory menjadi 2 Gb / 2048 MB, Setelah itu tekan tombol Next

![image](https://user-images.githubusercontent.com/56806850/201663968-6ae5da8e-b451-4309-85a0-e4fcae220d57.png)
Setelah memilih membuat virtual disk tekan next

![image](https://user-images.githubusercontent.com/56806850/201665501-948a8190-2377-48ed-9862-3484912473aa.png)
pada pilihan di atas bisa menggunakan tipe VDI untuk software Virtual box saja, apa bila ingin di gunakann Microsoft Virtual PC anda bisa memilih VHD, Untuk VMDK tipe file ini bisa di gunakan juga pada software VMwere. 

![image](https://user-images.githubusercontent.com/56806850/201666761-6fc79fd1-87e8-4948-a6b6-2021ade2d005.png)
![image](https://user-images.githubusercontent.com/56806850/201667037-c9404e2c-64cd-4149-b932-21abdc49104b.png)

untuk pemilihan penyimapanan saya menggunakan Dynamic allocated dimana ukuran akan berubah rubah hingga alokasi yg di tentukan, lalu tentukan ukuran hardisk menjadi 10 GB, lalu klik next

![image](https://user-images.githubusercontent.com/56806850/201667362-605d75e6-a1cf-4c1c-87bb-027fa21630de.png)
![image](https://user-images.githubusercontent.com/56806850/201667669-693fd4ae-695b-4af9-aea8-f043e16fa5d8.png)

Penyiapan Virtual box sudah siap, lalu kita rubah network kita dari NAT menjadi Bridge Adapter, dengan menekan tombol settings lalu pilih tab network. Setelah dirubah menjadi Bridge Network klik OK.

![image](https://user-images.githubusercontent.com/56806850/201668842-7c3669c6-e102-470d-8a7c-ecebbe98cf1d.png)
![image](https://user-images.githubusercontent.com/56806850/201669278-5febb662-a20f-47eb-8fcb-ef550d7b26d9.png)

Karena Optical Drive belum di pilih, maka kita plih ISO Ubuntu yang sudah di download terlebih dahulu. Dengan menekan tombol settings lalu tekan gambar icon ISO seperti gambar di atas.

![image](https://user-images.githubusercontent.com/56806850/201669438-d766cfb9-cb96-46ac-abd5-3cdad3afdc57.png)

Tekan tombol Add lalu cari ISO ubuntu Server yang sudah di download 

![image](https://user-images.githubusercontent.com/56806850/201669995-5d30cc8d-6f68-4ff3-9888-41cd87ec695c.png)

Lalu Tekan tombol choose


![image](https://user-images.githubusercontent.com/56806850/201670849-f96cadf4-fa61-4d1f-8fb4-6ba8c2c3fec5.png)
Disk Ubuntu sudah terpasang, lalu kita bisa lanjut ke langkah berikutnya

![image](https://user-images.githubusercontent.com/56806850/201670431-9a6d52ca-5f4c-4cfb-aca8-e13abca1b022.png)
Virtual box siap untuk di luncurkan . Lalu klik tombol start

Tahap 2 - Installasi Ubuntu Server

Setelah menekan tombol start akan muncul pilihan pertama, pilih yang paling atas. 
![image](https://user-images.githubusercontent.com/56806850/201671231-ef9bc487-e635-4c3e-9b49-961231c06d2f.png)

![image](https://user-images.githubusercontent.com/56806850/201673505-898e157c-ea03-4f1f-8d7d-290ec76b354d.png)
Tunggu proses hingga selesai



