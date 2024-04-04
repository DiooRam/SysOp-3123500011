<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 6<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="image/pens logo.png" alt="Logo PENS">
    <h3 style="text-align: center;">Disusun Oleh : </h3>
    <p style="text-align: center;">
        <strong>Roihanah Inayati Bashiroh (3123500005)</strong><br>
        <strong>Dio Ramadhan Widya Pamungkas (3123500011)</strong><br>
        <strong>Ragil Ridho Saputra (3122500016)</strong>
    </p>

<h3>Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik
Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
    <hr>
    <hr>
</div>

## Daftar isi

1. [Jawaban Tugas Pendahuluan](#tugas-pendahuluan)
2. [Laporan Hasil Percobaan](#percobaan)

### Percobaan 5 : Menghentikan dan Memulai Kembali Job

1. Perintah `yes > /dev/null`

    <img src="image/1.png" alt="">

   <br>
   Analisa : Cara lain meletakkan job pada background dengan memulai job secara normal (pada foreground), stop job dan memulai lagi pada background. Gunakan perintah yes > /dev/null untuk memulai job baru. Hentikan sementara job (suspend), bukan menghentikannya (terminate), tetapi menghentikan sementara job sampai di restart. Untuk menghentikan sementara job gunakan Ctrl + Z

   <br>

2. Perintah `fg`

    <img src="image/2.png" alt="">

   <br>
   Analisa : Perintah `fg` disini digunakan untuk me-restart job pada foreground.

   <br>

3. Perintah `bg`

    <img src="image/3.png" alt="">

   <br>
   Analisa : Setelah instruksi fg, Shell akan menampilkan nama perintah yang diletakkan di foreground. Stop job lagi dengan Ctrl + Z. Kemudian gunakan perintah bg untuk meletakkan job pada background.Job tidak bisa dihentikan dengan Ctrl + Z karena job berada pada background. Untuk menghentikannya, letakkan job pada foreground dengan fg dan kemudian hentikan sementara dengan Ctrl + Z.

   <br>

4. Perintah `yes &`

    <img src="image/4.jpg" alt="">

   <br>
   Analisa : Job pada background dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain seperti perintah di atas. Untuk menghentikannya tidak dapat menggunakan Ctrl + C. Job harus dipindah ke foreground baru diberhentikan dengan cara tekan fg dan tekan enter, Kemudian lanjutkan dengan Ctrl + Z untuk menghentikan sementara

   <br>

5. Perintah `fg %2, bg %2 atau %2`

    <img src="image/5.png" alt="">

   <br>
   Analisa :  Perintah di atas digumakan apabila ingin menjalankan banyak job dalam satu waktu, letakkan job pada foreground atau background dengan memberikan job ID.
   <br>

6. Perintah `fg`

    <img src="image/6.png" alt="">

   <br>
   Analisa : tekan fg dan tekan Enter, kemudian dilanjutkan dengan Ctrl-Z untuk menghentikan sementara

   <br>

7. Perintah `ps -fae`

    <img src="image/7.png" alt="">

   <br>
   Analisa :  Lihat job dengan perintah ps -fae dan tekan Enter. Kemudian hentikan proses dengan perintah kill. Pada proses di atas proses yang dihentikan adalah proses dengan PID 6142, yaitu proses yes > /dev/null

   <br>

### Percobaan 6 : Percobaan dengan Penjadwalan Prioritas

1. Login sebagai root

2. Buka tiga terminal,tampilkan pada screen yang sama

   <img src="image/8.png" alt="">

   <br>

3. Pada setiap terminal, ketik `PS1 = ” \w:”` diikuti Enter. `\w` menampilkan path pada direktori home.

   <img src="image/9.png" alt="">

    <br>

4. Karena login sebagai root, maka akan ditampilkan `~:` pada setiap terminal. Untuk setiap terminal ketik `pwd` dan tekan Enter untuk melihat bahwa Anda sedang berada pada direktori `/root`.

<img src="image/10.png" alt="">

  <br>
5. Buka terminal lagi (keempat), atur posisi sehingga keempat terminal terlihat pada screen

   <img src="image/11.png" alt="">
  
  <br>

6. Pada terminal keempat, ketik `top` dan tekan _Enter_. Maka program `top` akan muncul. Ketik `i`. Top akan menampilkan proses yang aktif. Ketik `lmt`. `Top` tidak lagi menampilkan informasi pada bagian atas dari screen. Pada percobaan ini, terminal ke empat sebagai jendela `Top`.


  <img src="image/12.png" alt="">

  <br>
      <img src="image/13.jpg" alt="">
  
  <br>
      <img src="image/14.png" alt="">

7. Pada terminal 1, bukalah program executable C++ dengan mengetik program `yes` dan tekan _enter_.
8. Ulangi langkah 7 untuk terminal 2

<img src="image/15.png" alt="">

9. Jendela Top akan menampilkan dua program `yes` sebagai proses yang berjalan. Nilai `%CPU` sama pada keduanya. Hal ini berarti kedua proses mengkonsumsi waktu proses yang sama dan berjalan sama cepat. _PID_ dari kedua proses akan berbeda, misalnya pada contoh di atas adalah 2366 dan 2366. Kemudian gunakan terminal 3 (yang tidak menjalankan primes maupun Jendela Top) dan ketik _renice 19 2366_ dan diikuti Enter. Hal ini berarti mengganti penjadwalan prioritas dari proses ke 19.

 <img src="image/16.png" alt="">

10. Tunggu beberapa saat sampai program top berubah dan terlihat pada jendela `Top`. Pada kolom `STAT` memperlihatkan `N` untuk proses 2366. Hal ini berarti bahwa penjadwalan prioritas untuk proses 2366 lebih besar (lebih lambat) dari 0. Proses 2368 berjalan lebih cepat.

      <img src="image/17.png.png" alt="">

11. Program _top_ juga mempunyai fungsi yang sama dengan program `renice`. Pilih Jendela _Top_ dan tekan `r`. Program top terdapat prompt PID to renice: tekan 2366 dan tekan Enter. Program top memberikan prompt Renice PID 1889 to value: tekan -19 dan tekan Enter.

       <img src="image/18.png" alt="">
        
      <br>
      <img src="image/19.png" alt="">

12. Tunggu beberapa saat sampai top berubah dan lihat nilai %CPU pada kedua proses. Sekarang proses 2366 lebih cepat dari proses 2368. Kolom status menunjukkan < pada proses 1889 yang menunjukkan penjadwalan prioritas lebih rendah (lebih cepat) dari nilai 0

       <img src="image/20.png" alt="">

13. Pilih terminal 3 (yang sedang tidak menjalankan yes atau program top) dan ketik nice –n -10 yes dan tekan Enter. Tunggu beberapa saat agar program top berubah dan akan terlihat proses primes ketiga. 

       <img src="image/21.png" alt="">

14. Jangan menggunakan mouse dan keyboard selama 10 detik. Program top menampilkan proses yang aktif selain program yes. Maka akan terlihat proses top terdaftar tetapi %CPU kecil (dibawah 1.0) dan konsisten. Juga terlihat proses berhubungan dengan dekstop grafis seperti X, panel dll.

       <img src="image/22.png" alt="">

15. Pindahkan mouse sehingga kursor berubah pada screen dan lihat apa yang terjadi dengan tampilan top. Proses tambahan akan muncul dan nilai %CPU berubah sebagai bagian grafis yang bekerja. Satu alasan adalah bahwa proses 2314 berjalan pada penjadwalan prioritas tinggi. Pilih jendela Top, ketik `r`. `PID to renice :` muncul prompt. Ketik 2314 dan tekan Enter. `Renice PID 2314 to value:` muncul prompt. Ketik 0 dan tekan Enter. Sekarang pindahkan mouse ke sekeliling screen. Lihat perubahannya

       <img src="image/23.png" alt="">

       <br>
       <img src="image/24.png" alt="">
       

16. Tutup semua terminal window.

17. Logout dan login kembali sebagai user.


### Latihan : Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya

1. Masuk ke tty2 dengan Ctrl+Alt+F2. Ketik ps –au dan tekan Enter. Kemudian perhatikan keluaran sebagai berikut :

     <img src="image/25.png" alt="">
   - Sebutkan nama-nama proses yang bukan root

     - Semua proses kecuali `/bin/login -p--` adalah bukan root

   - Tulis PID dan COMMAND dari proses yang paling banyak menggunakan CPU time

     - PID : 1135
     - COMMAND : -bash

   - Sebutkan buyut proses dan PID dari proses tersebut

     - `/usr/libexec/gdm-wayland-session` dengan PID 656

   - Sebutkan beberapa proses daemon

     - Pada beberapa proses yang tampil pada gambar di atas, tidak ada proses daemon.

   - Pada prompt login lakukan hal- hal sebagai berikut : `$ csh` `$ who` `$ bash` `$ ls` `$ sh` `$ ps`

     <img src="image/26.png" alt="">

     Analisa :
     Perintah `$ bash` digunakan untuk mengkonversi instruksi yang dimasukkan ke dalam bahasa biner yang dapat di mengerti oleh kernel Linux, perintah `$ ls` digunakan untuk menunjukkan semua file yang ada dalam direktori aktif, dan perintah `$ csh` adalah sebuah shell interaktif yang memiliki lebih banyak sintaks dibandingkan dengan Bourne Shell. PID, TTY, TIME, dan CMD membentuk empat kolom utama tampilan perintah ps, yang menampilkan daftar proses yang sedang berlangsung dalam sistem. Perintah `$ who` menampilkan daftar pengguna yang saat ini masuk ke sistem. Ini menunjukkan nama pengguna, terminal yang mereka gunakan, waktu login, dan informasi lainnya. Perintah ini digunakan dengan sering untuk mengetahui siapa yang sedang menggunakan sistem atau

   - Sebutkan PID yang paling besar dan kemudian buat urut-urutan proses sampai ke PPID = 1.

       <img src="image/27.png" alt="">

     - PID = 1557 (ps)
     - PID = 1556 (sh)
     - PID = 1553 (bash)
     - PID = 1551 (csh)
     - PID = 1128 (bash)


2. Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya :

   - `-f` daftar penuh

      <img src="image/28.png" alt="">

   - `-j` format job

       <img src="image/29.png" alt="">

   - `j` format job control

       <img src="image/30.png" alt="">

   - `l` daftar memanjang

       <img src="image/31.png" alt="">

   - `s` format sinyal

       <img src="image/32.png" alt="">

   - `v` format virtual memory

       <img src="image/33.png" alt="">

   - `X` format register i386

       <img src="image/34.png" alt="">

3. Lakukan urutan pekerjaan berikut :

   - Gunakan perintah `find` ke seluruh direktory pada sistem, belokkan output sehingga daftar direktori dialihkan ke file `directories.txt` dan daftar pesan error dialihkan ke file `errors.txt`

      <img src="image/35.png" alt="">

   - Gunakan perintah `sleep 5`. Apa yang terjadi dengan perintah ini ?

      <img src="image/35.png" alt="">

   - Jalankan perintah pada background menggunakan `&`

      <img src="image/36.png" alt="">

   - Jalankan `sleep 15` pada foreground, hentikan sementara dengan Ctrl-Z dan kemudian letakkan pada background dengan `bg`. Ketikkan `jobs`. Ketikkan `ps`. Kembalikan job ke foreground dengan perintah `fg`.

       <img src="image/37.png" alt="">

   - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan perintah `kill` untuk menghentikan proses diikuti job number.

     <img src="image/37.1.png" alt="">


   - Jalankan `sleep 15` pada background menggunakan `&` dan kemudian gunakan `kill` untuk menghentikan sementara proses. Gunakan `bg` untuk melanjutkan menjalankan proses.

     <img src="image/37.1.png" alt="">


   - Jalankan `sleep 60` pada background 5 kali dan terminasi semua pada dengan menggunakan perintah `killall`.

      <img src="image/38.png" alt="">
      <img src="image/38.1.png" alt="">


   - Gunakan perintah `ps`, `w` dan `top` untuk menunjukkan semua proses yang sedang dieksekusi.

      <img src="image/39.png" alt="">
          
      <img src="image/40.png" alt="">


   - Gunakan perintah `ps –aeH` untuk menampilkan hierarki proses. Carilah init proses. Apakah Anda bisa identifikasi sistem daemon yang penting ? Dapatkan Anda identifikasi shell dan subproses ?

     <img src="image/40.png" alt="">


   - Kombinasikan `ps –fae` dan grep, apa yang Anda lihat ?

     <img src="image/42.png" alt="">


   - Jalankan proses `sleep 300` pada background. Log off komputer dan log in kembali. Lihat daftar semua proses yang berjalan. Apa yang terjadi pada proses sleep ?

     <img src="image/43.png" alt="">

