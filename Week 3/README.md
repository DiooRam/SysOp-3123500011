<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 3<br>SysOp</h1>
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


## Daftar Isi

1. [PPT](#ppt)
2. [FLOPS dan IOPS](#flops-dan-iops)<br>
   [Install gcc, make, dan git](#install-gcc-make-dan-git)<br>
   [How to run FLOPS dan IOPS](#how-to-run-flops-dan-iops)<br>
   [Tabel Pengujian](#tabel-pengujian)<br>
   [Analisa](#analisa)
3. [Referensi](#referensi)

## PPT

[Link PPT](https://www.canva.com/design/DAF_Q_JAZRc/i6EOGG2lMCJPxMgpVESW0g/view?utm_content=DAF_Q_JAZRc&utm_campaign=designshare&utm_medium=link&utm_source=editor)

## FlOPS dan IOPS

### Install GCC, make, dan GIT

 <img src= "image/Install GCC,make, dn GIT.jpg" >


### How to run FLOPS dan IOPS

 <img src= "image/Flops dan iops.jpg" >

1. Ragil<br>
   Percobaan FLOPS64 5 kali<br>
   <img src= "image/Ragil FLOPS.png" >
   Percobaan IOPS64 5 kali<br>
   <img src= "image/Ragil IOPS.png" >
2. Hana<br>
   Percobaan FLOPS64 5 kali<br>
   <img src= "image/Hana FLOPS.png" >
   Percobaan IOPS64 5 kali<br>
  <img src= "image/Hana IOPS.png" >
3. Dio<br>
   Percobaan FLOPS64 5 kali<br>
   <img src= "image/Dio FLOPS.png" >
   Percobaan IOPS64 5 kali<br>
   <img src= "image/Dio IOPS.png" >


### Tabel Pengujian

| Nama Anggota | Max Single Core FLOPS | Max Single Core IOPS | Max CPU FLOPS | Max CPU IOPS |
| ------------ | --------------------- | -------------------- | ------------- | ------------ |
| Ragil        | 6.2                   | 5.5                  | 23.2          | 22           |
| Hana         | 6                     | 6.6                  | 12.1          | 13.2         |
| Dio          | 10.8                  | 10.1                 | 21.6          | 20.2         |


#### Analisa

Percobaan yang kami lakukan meliputi : Penggunaan program benchmark untuk mengetahui dan mengukur jumlah IOPS dan FLOPS pada CPU masing-masing anggota sebanyak 5 kali percobaan yang nantinya akan dicari jumlah maksimum dan minimum. Hasil yang didapat menunjukkan bahwa IOPS memiliki total throughput dan throughput single core yang lebih tinggi dibandingkan dengan FLOPS.

Kinerja sistem dalam melakukan operasi floating point 64-bit diatas dikarenakan penggunaan laptop yang digunakan setiap anggota memiliki perbedaan processor, membuat hasil percobaan menunjukkan variasi yang signifikan, dengan throughput CPU maksimum berkisar antara 9.98 hingga 23.22 Gigaflops. Sementara itu, operasi integer 64-bit menunjukkan fluktuasi yang lebih terkendali, dengan throughput CPU maksimum berkisar antara 12.72 hingga 13.22 Gigaiops.

### Kesimpulan

Kesimpulan dari percobaan tersebut adalah bahwa percobaan IOPS berkaitan dengan kinerja perangkat penyimpanan dalam melakukan operasi input/output, sementara percobaan FLOPS berkaitan dengan kinerja prosesor dalam melakukan operasi perhitungan floating point. Dalam percobaan yang dilakukan, hasil menunjukkan bahwa IOPS memiliki total throughput dan throughput single core yang lebih tinggi daripada FLOPS. Perbedaan dalam kinerja sistem terkait dengan operasi floating point 64-bit disebabkan oleh perbedaan processor pada laptop yang digunakan oleh setiap anggota. Hal ini menyebabkan hasil percobaan menunjukkan perbedaan hasil dalam throughput CPU maksimum, baik untuk operasi floating point maupun integer.



## Referensi

- [Apa itu CPU?](https://www.youtube.com/watch?v=Z5JC9Ve1sfI)
- [Siklus CPU](https://www.youtube.com/watch?v=jFDMZpkUWCw)
- [FLOPS dan IOPS](https://github.com/ferryastika/flops-iops)
