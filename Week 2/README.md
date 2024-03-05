<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 2<br>SysOp</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="image/pens.jpg" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Roihanah Inayati Bashiroh (3123500005)</strong><br>
    <strong>Dio Ramadhan Widya Pamungkas (3123500011)</strong><br>
    <strong>Ragil Ridho Saputra (3122500016)</strong>
  </p>

  <h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik
    Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr>
  <hr>
</div>

## Daftar Isi
1. [Komposisi MotherBoard](#Komposisi-MotherBoard)
2. [Perbedaan Legacy&UEFI](#soal)

# Komposisi MotherBoard
Sistem operasi adalah perangkat lunak yang bertanggung jawab untuk mengelola sumber daya perangkat keras dan menyediakan
antarmuka bagi pengguna dan aplikasi untuk berinteraksi dengan komputer. Ini mengkoordinasikan tugas-tugas seperti
alokasi memori, penjadwalan CPU, manajemen file, dan penyediaan layanan jaringan, memungkinkan pengguna untuk
menjalankan program dengan efisien dan menjalankan fungsi-fungsi dasar seperti mengetik, menyimpan, dan mengakses data.


1.Socket CPU: Ada ZIF (Zero Insertion Force), LIF (Low Insertion Force), dan AMD Socket A.
<img src="image/1.png">

2.BIOS (Basic Input-Output System): Program dasar yang menghubungkan motherboard dengan sistem operasi.
<img src="image/2.png">

3.North Bridge Controller: Menghubungkan slot RAM, AGP, dan socket CPU.
<img src="image/3.png">

4.South Bridge Controller: Mengatur peripheral seperti USB, keyboard, IDE controller, dll.
<img src="image/4.png">

5.Konektor Power Supply Unit: Menyambungkan motherboard dengan power supply, AT atau ATX.
<img src="image/5.png">

6.Socket CPU: Ada ZIF (Zero Insertion Force), LIF (Low Insertion Force), dan AMD Socket A.
<img src="image/1.png">

7.BIOS (Basic Input-Output System): Program dasar yang menghubungkan motherboard dengan sistem operasi.
<img src="image/2.png">

8.North Bridge Controller: Menghubungkan slot RAM, AGP, dan socket CPU.
<img src="image/3.png">

9.South Bridge Controller: Mengatur peripheral seperti USB, keyboard, IDE controller, dll.
<img src="image/4.png">
10.Konektor Power Supply Unit: Menyambungkan motherboard dengan power supply, AT atau ATX.
<img src="image/5.png">


# Perbedaan Legacy&UEFI
<img src="image/5.png">
Definisi Unified Extensible Firmware Interface (UEFI) adalah proses booting pada komputer modern dengan kemampuan lebih canggih dibanding sistem Legacy.
UEFI menggunakan firmware URFI untuk menyimpan EFI Service Partitions saat proses booting berlangsung.
Sementara, Legacy adalah proses booting komputer dengan firmware BIOS yang lebih lama dan tradisional.
Waktu yang Dibutuhkan UEFI membutuhkan waktu booting yang lebih cepat. Sedangkan, Legacy lebih lama.
Dukungan untuk Penyimpanan UEFI sudah menggunakan partisi GUID Partition Table (GTP), sehingga dapat mendukung perangkat penyimpanan hingga 9 zettabytes.
Legacy yang masih menggunakan dukungan Master Boot Record (MBR) dapat mendukung perangkat penyimpanan komputer hanya 2 TB.
Keamanan UEFI dapat mencegah pemuatan aplikasi yang tak sah atau dicurigai.
Selain itu juga dapat menghambat adanya kerja dua boot karena UEFI menganggap sistem operasi adalah aplikasi.
ADVERTISEMENT Namun, pada Legacy, tak ada keamanan yang disediakan saat booting berlangsung, sehingga ada kemungkinan aplikasi tak sah dimuat serta terjadi dual-boot.

