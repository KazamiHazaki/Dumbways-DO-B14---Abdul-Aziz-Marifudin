Fork Dumbflix Repository 

Buka halaman `https://github.com/dumbwaysdev/dumbflix-frontend` pada bagian ujung sebelah kanan ada tombol bernama fork, kemudain tekan tombol tersebut.

![image](https://user-images.githubusercontent.com/56806850/202982704-1fec7e78-8731-4cc1-9c6b-8a9bf2459e57.png)

Beri nama repository lalu tekan create fork 

![image](https://user-images.githubusercontent.com/56806850/202982812-8be6e050-5c0d-4a66-871c-72306e9c06d2.png)


Sesudah di fork maka anda akan melihat repository tersebut di dalam repository pribadi.

![image](https://user-images.githubusercontent.com/56806850/202982922-b41816e7-a5df-406b-8ecb-c30dc0ae0640.png)

.


Deploy to cloudflare pages 

Setelah mendaftar buka pada tabh sebelah kiri yaitu pages

![image](https://user-images.githubusercontent.com/56806850/202983265-d0020b08-ac13-4594-9f8c-cc358213a8c0.png)

kemudian tekan create project, lalu anda akan diminta untuk menghubunngkan github/gitlab anda, untuk mendeploy dari github langsung ke cloudflare pages 

![image](https://user-images.githubusercontent.com/56806850/202983445-de298d57-e975-44f2-b7bc-6fc596de9038.png)

yang akan dicoba pada latihan ini adalah repository dumbflix-frontend, maka pilih repository tersebut setelah itu tekan tombol next

![image](https://user-images.githubusercontent.com/56806850/202983534-00f09c9d-e9ca-4397-a568-70214a0121ab.png)

Pada build settings rubah Framework Preset menjadi `create react app` karena pada dumbflix menggunakan basecode react 

![image](https://user-images.githubusercontent.com/56806850/202983703-d5de0874-b31d-4691-b8d5-ef6561fc342c.png)

setelah pengaturan build selesai maka bisa di save dan di deploy

![image](https://user-images.githubusercontent.com/56806850/202983929-50080761-59b5-4882-b1f6-06b113516b81.png)

tunggu proses building dan deploy 

![image](https://user-images.githubusercontent.com/56806850/202984000-f20e25c4-7cfc-4123-bd46-64f3d29f82d6.png)

jika sudah muncul success maka aplikasi sudah di deploy dengan link yg di bagikan dari cloudflare 

![image](https://user-images.githubusercontent.com/56806850/202984293-93d41bb2-6346-4ace-b604-c811ecdc11c3.png)


ketika di klik link tersebut website dari repository yg di fork akan muncul

![image](https://user-images.githubusercontent.com/56806850/202987173-bae4ece9-3f1d-4bbb-840e-7e2022edc155.png)


![image](https://user-images.githubusercontent.com/56806850/202987058-7c954466-64ee-4eea-800d-5c121e77a989.png)


pada title web tersebut masih menggunakan nama `Fadhil Darma` mari kita rubah menjadi nama kita.

ubah pada file index.html yg berada pada direktori public, lalu save perubahan tersebut

![image](https://user-images.githubusercontent.com/56806850/202985187-c170f29f-2f60-43c8-80f3-9cec95323d00.png)

setelah ada perubahan pada repository kita maka cloudflare pages akan secara otomatis mengikuti update repository tersebut. Jadi cloudflare akan membuild kembali dari awal sehingga perubahan tersebut akan langsung terlihat 

![image](https://user-images.githubusercontent.com/56806850/202985643-3361f917-a81c-464b-9d1e-9bd2c4c97e9c.png)

pada gambar di atas terjadi proses deployment baru sesudah kita merubah title pada index.html tersebut. ketika source `master 6b6b9fe` di tekan maka akan muncul perubahan yg sudah di lakukan pada file index.html 

![image](https://user-images.githubusercontent.com/56806850/202985845-412938d3-6ef3-4bab-91cc-5a29f3e27acd.png)

setelah deployment selesai maka perubahan tersebut langsung di update pada website dumbflix 

![image](https://user-images.githubusercontent.com/56806850/202985928-e95ed9e3-b664-4059-b262-14fdd954a9cd.png)
 
 yang sebelumnya bertitle `Fadhil Darma` berubah menjadi nama saya.
 
 
 Deploy 2 branch berbeda 
 
 pertama buat terlebih dahulu branch tersebut 
 
 ![image](https://user-images.githubusercontent.com/56806850/202988455-01d0d263-593d-4716-96a9-d5fcf1ba3282.png)

lalu setelah membuat 2 branch tambahan kita ubah pengaturan pada website cloudflare. Masuk ke bagian settings 

![image](https://user-images.githubusercontent.com/56806850/202991885-36db565c-fc08-4f54-9625-f77613f22ea6.png)

lalu ke tab Builds & Deployments 

![image](https://user-images.githubusercontent.com/56806850/202991951-85281836-2c5b-46aa-b64e-b23d1dcf1a46.png)


pada preview branch rubah dari `All non-Production branches` menjadi custom branches. kemudian tambahkan branch yang sudah di buat pada repo dumbflix yaitu branch ` Developement` & `Staging`

![image](https://user-images.githubusercontent.com/56806850/202992174-bd2369e7-f311-400c-8503-a68351553af7.png)


kembali lagi pada tab deployments dumbflix pada cludflare pages setelah membuat 2 tambahan branch pada repository dumbflix cloudflare secara otomatis juga menambahkan branch tersebut ke cloudflare pages 

![image](https://user-images.githubusercontent.com/56806850/202992522-28f7052d-e35f-4491-9748-bedcf9128a77.png)

ketika menekan tombol view details pada salah satu branch yg sudah di update pada cloudflare pages maka branch baru akan mendapatkan domain tersendiri jika pada branch utama `dumbflix-frontend-d5b.pages.dev` maka pada branch lainnya akan mendapatkan tambahan subdomain sesuai dengan nama branch tersebut. Contoh pada branch staging yg dibuat. 

![image](https://user-images.githubusercontent.com/56806850/202992960-22ec9f93-2cf4-49bb-a4be-ce0a583e7183.png)

makaa ketika anda melakukan pengeditan pada branch staging, cloudflare akan mengupdate perubahan tersebut pada branch staging dan akan di tampilkan pada halaman staging sendiri yaitu `
staging.dumbflix-frontend-d5b.pages.dev`

untuk mencobanya mari kita lakukan perubahan pada index.html di branch staging, tambahkan `(Staging)` pada title index.html 

![image](https://user-images.githubusercontent.com/56806850/202993526-6ce376b2-8273-4f52-87ea-610369909a36.png)

setelah deployment pada branch staging selesai maka perubahan pada web staging jg terjadi

![image](https://user-images.githubusercontent.com/56806850/202994484-78b636c3-40be-4a21-9116-eb354288579d.png)

tittle pada branch staging 

![image](https://user-images.githubusercontent.com/56806850/202994542-359ea46c-c468-42fe-9024-3f296d08e31a.png)






