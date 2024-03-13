<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 2<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="Logo_PENS.png" alt="Logo PENS">
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

## Daftar Isi

1. [PPT](#ppt)
2. [FLOPS dan IOPS](#flops-dan-iops)
   - [Install gcc, make, dan git](#install-gcc-make-dan-git)
   - [How to run FLOPS dan IOPS](#how-to-run-flops-dan-iops)
   - [Tabel Pengujian](#tabel-pengujian)
   - [Analisa](#analisa)
3. [Referensi](#referensi)

## PPT

[Link PPT](https://www.canva.com/design/DAF_FjVZneE/mGYFV4pIDyYAnDvjwu0qfg/view?utm_content=DAF_FjVZneE&utm_campaign=designshare&utm_medium=link&utm_source=editor)

## FlOPS dan IOPS

### Install GCC, make, dan GIT

![App Screenshot](assets/img/install_gcc_make_git.png)

### How to run FLOPS dan IOPS

![App Screenshot](assets/img/run_flops_iops.jpg)

1. Awang
   Percobaan FLOPS64 5 kali
   ![App Screenshot](assets/img/awang_flops.jpg)
   Percobaan IOPS64 5 kali
   ![App Screenshot](assets/img/awang_iops.jpg)
2. Hawa
   Percobaan FLOPS64 5 kali
   ![App Screenshot](assets/img/flops64_1.png)
   ![App Screenshot](assets/img/flops64_2.png)
   Percobaan IOPS64 5 kali
   ![App Screenshot](assets/img/flops64_3.png)
   ![App Screenshot](assets/img/flops64_4.png)
3. Vonda
   Percobaan FLOPS64 5 kali
   ![App Screenshot](assets/img/vonda1.png)
   ![App Screenshot](assets/img/vonda2.png)
   Percobaan IOPS64 5 kali
   ![App Screenshot](assets/img/vonda3.png)
   ![App Screenshot](assets/img/vonda4.png)

### Tabel Pengujian

| Nama Anggota | Max Single Core FLOPS | Max Single Core IOPS | Max CPU FLOPS | Max CPU IOPS |
| ------------ | --------------------- | -------------------- | ------------- | ------------ |
| Awang        | 5.3                   | 5.2                  | 10.5          | 10.3         |
| Hawa         | 2.2                   | 1.9                  | 4.3           | 3.8          |
| Vonda        | 6                     | 4.5                  | 11.9          | 9            |

#### Analisa

Dari data yang ditunjukkan oleh table diatas menunjukkan bahwa setiap laptop dengan ketidaksamaan processor menyebabkan hasil dari test FLOPS dan IOPS berbeda-beda tergantung kecepatan dari masing-masing CPU/processor.
Mulai dari **Awang** dengan spesifikasi **Processor 11th Gen Intel(R) Core(TM) i3-1115G4 @ 3.00GHz, 2995 Mhz, 2 Core(s), 4 Logical Processor(s)**, untuk spesifikasi yang ada di debian menggunakan 2 core, bisa memperoleh angka 5.3 Gigaflops dan 5.2 Gigaiops di single core dan Max CPU berada di angka 10.5 Gigaflops dan 10.3 Gigaiops.
Lalu **Hawa** dengan spesifikasi **Processor 11th Gen Intel(R) Core(TM) i3-1115G4 @ 3.00GHz, 2995 Mhz, 2 Core(s), 4 Logical Processor(s)**, untuk spesifikasi yang ada di debian menggunakan 2 core, bisa memperoleh angka 4.3 Gigaflops dan 3.8 Gigaiops di single core dan Max CPU berada di angka 2.2 Gigaflops dan 1.9 Gigaiops.
lalu **vonda** dengan spesifikasi **13th Gen Intel(R) Core(TM) i5-13500H, 2600 Mhz, 12 Core(s), 16 Logical Proces**, untuk spesifikasi yang ada di debian menggunakan 2 core, bisa memperoleh angka 6 Gigaflops dan 4.5 Gigaiops di single core dan Max CPU berada di angka 11.9 Gigaflops dan 9 Gigaiops.

### Kesimpulan

Dari percobaan kelompok kami, bisa ditarik kesimpulan bahwa Perbandingan antara FLOPS dan IOPS tidak langsung karena keduanya mengukur aspek yang berbeda dari kinerja sistem komputasi. FLOPS lebih berkaitan dengan kemampuan prosesor untuk melakukan perhitungan matematika, sedangkan IOPS lebih berkaitan dengan kemampuan sistem penyimpanan untuk mengakses dan memanipulasi data. Meskipun keduanya merupakan ukuran kinerja yang penting dalam konteks tertentu, mereka tidak dapat secara langsung dibandingkan atau ditukar-tukar karena masing-masing mengukur aspek yang berbeda dari kinerja sistem komputasi.

## Referensi

- [Apa itu CPU?](https://www.youtube.com/watch?v=Z5JC9Ve1sfI)
- [Siklus CPU](https://www.youtube.com/watch?v=jFDMZpkUWCw)
- [FLOPS dan IOPS](https://github.com/ferryastika/flops-iops)
