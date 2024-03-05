<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 1<br>SysOp</h1>
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
    <h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  </hr>
  <hr>

  </div>

  
  # Daftar Isi
  1. [Pendahuluan](#sistem-operasi)
  2. [Soal](#soal)
  3. [Referensi](#referensi)
  
  
  # Sistem Operasi
  Sistem operasi adalah perangkat lunak yang bertanggung jawab untuk mengelola sumber daya perangkat keras dan menyediakan
  antarmuka bagi pengguna dan aplikasi untuk berinteraksi dengan komputer. Ini mengkoordinasikan tugas-tugas seperti
  alokasi memori, penjadwalan CPU, manajemen file, dan penyediaan layanan jaringan, memungkinkan pengguna untuk
  menjalankan program dengan efisien dan menjalankan fungsi-fungsi dasar seperti mengetik, menyimpan, dan mengakses data.
  
  # SOAL
  # 1. Sebutkan dan jelaskan proses booting!
  Proses booting adalah serangkaian langkah yang dilakukan oleh komputer ketika dinyalakan untuk mempersiapkan sistem agar
  siap digunakan. Proses ini meliputi:
  
  1. Menyalakan Komputer
  Kamu menyalakan komputer, PC, atau laptop dengan menekan tombol power.
  <img src="image/power.jpg">
  
  2. Cek Power
  Selanjutnya, power supply akan mengeluarkan sinyal bahwa aliran listrik yang masuk berjalan dengan aman dan normal. Itu
  tandanya komputer siap bekerja.
     CPU Menyala
  Kemudian, apabila aliran daya normal, CPU akan mulai aktif untuk bekerja.
  <img src="image/ijo.jpg">
  
  3. Cek Perangkat Keras
  Setelahnya, sistem akan memulai pengecekan semua komponen perangkat keras, seperti RAM, penyimpanan atau storage, dan
  komponen lain oleh POST BIOS.
  <img src="image/bios.jpg">
  
  4. Loading Driver
  Setelah semua perangkat keras diperiksa dan mampu berjalan baik, masing-masing driver dari komponen akan dijalankan.
     GPU Berjalan
  GPU atau kartu grafis kemudian aktif dengan menampilkan secara visual proses booting di layar. Kartu grafis juga dikenal
  dengan VGA.
     Pemuatan dan Loading Sistem Operasi
  Berikutnya, proses pencarian boot sector yang selanjutnya akan memuat data atau loading sistem operasi yang ada pada
  komputer. Kalau komputermu menggunakan Windows maka akan muncul logo Windows.
  <img src="image/loading.jpg">
  
  5. Masuk Desktop
  Terakhir, adalah kamu akan menemukan desktop komputer. Itu artinya, proses booting sukses.
  <img src="image/windows.jpg">
  
  Proses booting memungkinkan komputer untuk memulai operasi normalnya dan siap digunakan oleh pengguna.
  
  # 2. Bagaimana cara install Debian 12 di Virtualbox
  
  1.Buka virtual box dan pilih tombol new untuk membuat virtual device
  <img src="image/1.png">
  
  2.Beri nama untuk project nya dan pilih iso debian yang ada di storage dan checklist kolom skip
  <img src="image/2.png">
  
  3.Atur berapa ram yang ingin di gunakan(sesuaikan dengan ram device) dan core cpu
  <img src="image/3.png">
  
  4.Jika sudah maka klik finish untuk menyelesaikan setup
  <img src="image/4.png">
  
  5.Akan terdapat pilihan proses booting nya debian pada halaman awal tadi
  <img src="image/5.png">
  
  6.Klik 2 kali dan akan memasuki proses penginstalan debian dan pilih graphic install dan akan memunculkan halaman
  tersebut dan pilih english
  <img src="image/6.png">
  
  7.Pilih yes pada bagian install the GRUB boot loader dan pilih continue
  <img src="image/7.png">
  
  8.Pilih Asia kemudian Indonesia sebagai lokasi kita dan klik continue
  <img src="image/8.png">
  
  9.Saat konfigurasi lokal,pilih United States
  <img src="image/9.png">
  
  10.Pada bagian konfigurasi keyboard,pilih American English
  <img src="image/10.png">
  
  11.Tunggu instalasi sampai selesai,bila sudah selesai masukkan konfigurasi network untuk hostname dan untuk domain kita
  kosongkan
  <img src="image/11.png">
  <img src="image/13.png">
  <img src="image/14.png">

  
  12.Atur Password untuk masuk(yang mudah di ingat)
  <img src="image/15.png">
  
  13.Masukkan nama lengkap,username dan password(bedakan dari password sebelum nya) untuk setup user
  <img src="image/16.png">
  <img src="image/17.png">
  <img src="image/18.png">
  
  14.Pilih zona untuk jam,dan pilih Western(tergantung tempat)
  <img src="image/19.png">
  
  15.Untuk partition disk pilih manual dan pilih SCSI3 dan pilih yes pada create new empy partition table
  <img src="image/20.png">
  <img src="image/21.png">
  <img src="image/22.png">
  
  16.Pilih pri/log,kemudian create new partition,atur ke 20GB,pilih primary,kemudian pilih beginning dan bootable flag
  ubah ke on dan pilih done
  <img src="image/23.png">
  <img src="image/24.png">
  <img src="image/25.png">
  <img src="image/26.png">
  <img src="image/27.png">

  17.Setelah di partisi menjadi beberapa bagian,kemudian pilih finish dan tunggu instalasi sampai selesai
  <img src="image/36.png">
  <img src="image/43.png">
  
  18.Pilih no pada scan extra installation,pilih indonesia untuk debian archive dan pilih kebo.pens dan kosongkan http
  proxy
  <img src="image/44.png">
  <img src="image/45.png">
  <img src="image/46.png">
  <img src="image/47.png">
  
  19.Tunggu konfigurasi sampai selesai
  <img src="image/48.png">
  
  20.Setelah selesai,pilih yes pada participate in the package,pada software selection biarkan default
  <img src="image/49.png">
  <img src="image/50">
  
  21.Tunggu sampai proses installasi software selesai(membutuhkan waktu sedikit lama)
  <img src="image/51">
  
  22.Setelah selesai,pilih /dev/sda kemudian di halaman finish,klik continue dan debian sudah terinstall
  <img src="image/52">
  <img src="image/53">
  <img src="image/54">
  
  # Referensi
  
  [Debian Download](https://www.debian.org/download)
  
  [VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)
  
  [Materi Booting](https://inigadgets.com/mengenal-apa-itu-booting/)
