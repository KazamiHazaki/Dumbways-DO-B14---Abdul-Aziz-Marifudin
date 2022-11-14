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


Lalu munncul pemilihan bahasa, pilih english dan tekan Enter

![image](https://user-images.githubusercontent.com/56806850/201685405-b75f755b-87df-4ddb-834c-33157ce94035.png)

![image](https://user-images.githubusercontent.com/56806850/201685664-d7a72de3-9b6e-4777-b808-a5ff3cc20092.png)

Pilihan berikutnya di tanya apakah mau untuk mengupdate ke versi terbaru ubuntu 22.10. Kita akan tetap menggunakan di versi 20.04 saja. langsung klik enter "Continue without updating"

![image](https://user-images.githubusercontent.com/56806850/201685905-13e586d6-04f9-466b-94ab-1a166258440f.png)

untuk keyboard kita pilih default saja yaitu engnlish, langsung tekan enter saja

![image](https://user-images.githubusercontent.com/56806850/201686173-a7e20626-2e0f-4f19-9077-aede8f6ddb55.png)

setelah memilih layout keyboard kita di tanya memilih instalasi type yang mana. kita pilih Ubuntu Server saja, dan langsung tekan Enter saja pada tombol "Done"

![image](https://user-images.githubusercontent.com/56806850/201689170-c21eac95-487a-4302-855c-8cba89f1bc9c.png)
![image](https://user-images.githubusercontent.com/56806850/201689321-15545ad3-d761-4847-95d4-288076d9fbab.png)

Pada pengaturan Network, kita rubah menjadi DHCP static, tekan enter pada enp0s3. pilih Edit Ipv4.

![image](https://user-images.githubusercontent.com/56806850/201689394-c02912c7-966f-467d-b312-ca8d394db3a0.png)

lalu pilih Manual.

![image](https://user-images.githubusercontent.com/56806850/201690466-c4373527-ed05-4d47-a5be-cd16e26625d6.png)


isi seperti berikut 

Subnet : 192.168.1.0/24
Address : 192.168.1.6
Gateway : 192.168.1.1
Name Server : 8.8.8.8

Lalu save 

![image](https://user-images.githubusercontent.com/56806850/201691353-63b577be-9039-4a67-b943-5f1e2e63b624.png)

Jika sudah maka tampilan DHCPv4 berubah menjadi static, lalu kita bisa lanjut ke tahap selanjutnya

![image](https://user-images.githubusercontent.com/56806850/201691564-75895765-d1b3-4a30-892f-35b0887c1ee3.png)

untuk proxy kita lewati saja, langsung klik done

![image](https://user-images.githubusercontent.com/56806850/201691829-dfaf9acb-de3d-4da6-9ce7-c71a4fa5ab10.png)

Mirror addresss kita pilih yg paling atas dan tekan enter

![image](https://user-images.githubusercontent.com/56806850/201692279-baee52b5-847a-4c30-a724-ec3949c62b3f.png)

untuk storage kita custom storage layout. arahkan tandaa X ke bawah bagian custom storage layou dengan menekan keyboard arah bawah dan tekan enter. lalu tekan done

![image](https://user-images.githubusercontent.com/56806850/201692585-08880142-8feb-440a-ac0a-20f5db1ab900.png)
![image](https://user-images.githubusercontent.com/56806850/201692709-b07d0f8c-6903-4bc3-a11f-807d97c01ef5.png)

lalu kita arahkan ke free space, dan tekan enter. pilih Add GPT Partition

![image](https://user-images.githubusercontent.com/56806850/201692830-aac08468-4c9c-4604-92c0-76045bdc01d5.png)

![image](https://user-images.githubusercontent.com/56806850/201693491-abf72280-aa33-4551-9a36-56a2a689a1e2.png)

Isi 2G untuk ukuran disk SWAP.Setalah di isi tekan save.

![image](https://user-images.githubusercontent.com/56806850/201694156-9c22dd3c-a9f8-4f9f-baa2-2f5c2d1ca776.png)

Lalu kita tambahkan partisi root untuk penyimpanan

![image](https://user-images.githubusercontent.com/56806850/201694481-66dbe23e-4614-4ed5-9b9b-71dca1d93208.png)
![image](https://user-images.githubusercontent.com/56806850/201694674-6c75570b-fc21-4864-886d-df088d2b986b.png)

lalu kita check kembali partisi disk yang kita buat, jika sudah seperti di atas kita bisa lanjutkan ke tahap berikutnya.

![image](https://user-images.githubusercontent.com/56806850/201694946-33be35bb-361e-44f6-9461-e552430fe0f2.png)
Kemudian isi data anda, seperti nama, server name, username, dan password. setelah itu lanjut berikutnya.

![image](https://user-images.githubusercontent.com/56806850/201695348-6146bab0-1205-4fd7-b798-e20d5fd5d0b8.png)

Kemudian install OpenSSH server, tekan enter pada kolom install Open SSH Server hingga muncul tanda "X", untuk import SSH identity kita biarkan saja. lalu tekan Done.

![image](https://user-images.githubusercontent.com/56806850/201695944-0664fb55-e9e1-4b20-ac8c-f75a746cb856.png)

Untuk featured tambahan kita lewati saja dan langsung tekan tombol done.

![image](https://user-images.githubusercontent.com/56806850/201696047-bdf39cbf-521e-4365-9ccd-4370e4020eba.png)

Tunggu proses installasi selesai.

![image](https://user-images.githubusercontent.com/56806850/201702507-809a7587-00dd-4cc5-979b-fc1baec2f968.png)
![image](https://user-images.githubusercontent.com/56806850/201702630-f44a948e-fc92-4266-b822-f7084f8fd95e.png)


jika terjadi Error disable CD-Room, maka kita harus mencopot ISO ubuntu server kita di bagian settings. Close terlebih dahulu dan matikan VMbox.

![image](https://user-images.githubusercontent.com/56806850/201702777-9cfd46ba-d248-44eb-a07b-3f1842fcfabd.png)
 
 masuk ke settings dan remove ISO Ubuntu. setelah itu kita start lagi VM Ubuntu nya.

![image](https://user-images.githubusercontent.com/56806850/201703116-871d6657-f217-468e-af72-0b83668f6818.png)

Ubuntu telah berhasil di install.

![image](https://user-images.githubusercontent.com/56806850/201702181-c9381764-e27a-4c60-8b89-5e60d9c40ef4.png)


Kita coba mengetest koneksi internet dengan ping ke google.com, dan Instalasi selesai

