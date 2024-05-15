<div align="center">
    <h1 style="text-align: center;font-weight: bold">Praktikum 9<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="pens logo.png" alt="Logo PENS">
    <h3 style="text-align: center;">Disusun Oleh : </h3>
    <p style="text-align: center;">
        <strong>Roihanah Inayati Bashiroh (3123500005)</strong><br>
        <strong>Dio Ramadhan Widya Pamungkas (3123500011)</strong><br>
        <strong>Ragil Ridho Saputra (3122500016)</strong>
    </p>

<h3>Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik
Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2024/2025</h3>
    <hr>
    <hr>
</div>


## Producer Consumer Semaphore

![App Screenshot](1.png)




Analisa: Program ini merupakan contoh implementasi dari masalah Producer-Consumer menggunakan semaphore dalam bahasa C. Dalam program ini, terdapat tiga opsi menu: "Producer", "Consumer", dan "Exit". Ketika opsi "Producer" dipilih, program akan menciptakan data dengan maksimum tiga data. Jika pengguna terus memilih opsi "Producer" tanpa memilih opsi lain lebih dari tiga kali, program akan menampilkan pesan "Buffer your full!!". Sebaliknya, jika opsi "Consumer" dipilih dan pengguna terus memilihnya tanpa memilih opsi lain lebih dari tiga kali, program akan menampilkan pesan "Buffer is empty!!". Opsi "Exit" digunakan untuk keluar dari program.

## Producer Consumer Wake-Sleep thread

![App Screenshot](2.png)

Analisa : Contoh program ini mengimplementasikan permasalahan Produsen Konsumen menggunakan semaphore dan thread dalam bahasa C++. Dalam skenario ini, thread digunakan untuk menjalankan produsen dan konsumen secara bersamaan. Dengan menggunakan konsep kunci gembok (mutex) dan variabel kondisi sebagai lampu lalu lintas, program menjamin bahwa hanya satu proses yang dapat mengakses sumber daya pada satu waktu tertentu. Ketika produsen menghasilkan barang, ia memberi tahu konsumen bahwa barang baru telah tersedia. Begitu pula ketika konsumen mengonsumsi barang, ia memberi tahu produsen bahwa barang tersebut telah diambil. Dengan demikian, program memastikan bahwa proses produksi dan konsumsi berjalan dengan aman dan terkoordinasi.

### Referensi

- [Producer Consumer Problem](https://www.geeksforgeeks.org/producer-consumer-problem-in-c/)