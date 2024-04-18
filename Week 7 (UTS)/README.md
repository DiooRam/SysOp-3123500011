<div align="center">
    <h1 style="text-align: center;font-weight: bold">UTS Sistem Operasi<br>SysOp</h1>
    <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
    <img src="Week 7 UTS/image/pens logo.png" alt="Logo PENS">
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


### Soal 
1. Fork : Parent - Child Process
Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.
<br>
2. Tugas
Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan fork().

### Jawaban nomor 1
1.
<img src="Week 7 UTS/image/0.1.png" alt="">
Fork merupakan salah satu konsep fundamental dalam sistem operasi Unix yang memungkinkan proses untuk membuat salinan dirinya sendiri. Dalam konteks bahasa pemrograman C, fungsi fork() digunakan untuk menciptakan proses baru yang disebut sebagai child process. Child process ini merupakan salinan identik dari proses parent yang memanggilnya, termasuk kode program dan lingkungan eksekusinya. Setelah proses child terbentuk, kedua proses (parent dan child) akan berjalan secara independen satu sama lain, memiliki ruang alamat memori yang terpisah, namun saling berbagi sumber daya sistem yang sama. Fork sangat berguna dalam paradigma pemrograman multiproses, memungkinkan aplikasi untuk melakukan tugas-tugas secara bersamaan atau paralel.

Implementasi fork dalam bahasa pemrograman C cukup sederhana. Berikut adalah contoh kode sederhana yang menggunakan fork untuk membuat proses child:

Contoh Implementasi menggunakan bahasa C : 
<br>
```
#include <stdio.h> 
#include <unistd.h> 

int main() { 
	int i; 

	for (i = 0; i < 3; i++) { 
		pid_t child_pid = fork(); 

		if (child_pid == 0) { 
			printf("Child process %d: PID=%d\n", i + 1, getpid()); 
			break; // Each child process should exit the loop 
		} else if (child_pid < 0) { 
			perror("Fork failed"); 
		} 
	} 

	if (getpid() != 1) { 
		// This code is executed only by the parent process 
		printf("Parent process: PID=%d\n", getpid()); 
	} 

	return 0; 
} 

```


<img src="Week 7 UTS/image/8.png" alt="">

Analisa : Program ini mencetak informasi tentang PID (Process ID), Child ID, dan PPID (Parent Process ID) saat proses utama dipanggil dengan PID 2488 dan parent ID 2246. Saat proses utama menggunakan fungsi fork(), informasi tersebut dicetak dengan penjelasan yang menunjukkan proses induk dan anak, masing-masing memiliki PID dan PPID. Proses induk memiliki PID 2488 dan PPID 2246, sama dengan proses utama. Proses anak memiliki PID 2489 dan PPID 1130, dengan PID yang jelas lebih besar daripada proses induk.

- hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.

1. fork01

```
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>


/* getpid() adalah system call yg dideklarasikan pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t mypid;
	uid_t myuid;
	for (int i = 0; i < 3; i++) {
		mypid = getpid();
		cout << "I am process " << mypid << endl;
		cout << "My parent process ID is " << getppid() << endl;
		cout << "The owner of this process has uid " << getuid()
	<< endl;
/* sleep adalah system call atau fungsi library
yang menghentikan proses ini dalam detik
*/
	sleep(3);
	}
return 0;
}

```

<img src="Week 7 UTS/image/1.png" alt="">

Visualisasi :


```
int main() { 
    for(int i = 0; i < 3; i++) {

                    pid: 6864, ppid: 1931, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)
                                    |
                    pid: 6864, ppid: 1931, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)
                                    |
                    pid: 6864, ppid: 1931, uid: 1000
                            [Main Process]
                                    |
                                 sleep(3)

    }
  return 0;
}
```
Analisa: Tampilan di atas menunjukkan bahwa program sedang melakukan proses forking berulang, menghasilkan sejumlah besar proses anak yang memiliki identitas yang berbeda-beda. Setiap proses mencatat PID (Process ID) dan PPID (Parent Process ID) miliknya, serta UID (User ID) yang sama untuk pemilik proses. Ini mencerminkan prinsip dasar dari panggilan sistem "fork" di mana sistem operasi menciptakan salinan dari proses yang sedang berjalan.

2. fork02

```
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	int x = 5;
	childpid = fork();

	while (1) {
		cout << "This is process ID" << getpid() << endl;
		cout << "In this process the value of x becomes " << x << endl;	
		sleep(2);
		x++;
	}
	return 0;
}

```

<img src="Week 7 UTS/image/2.png" alt="">

Visualisasi :

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
    while(1) {                /     \
               pid: 6987, ppid: -    pid: 6988, ppid: 6988
            [Parent Process] x = 5    [Child Process] x = 5
                              \     /
                               \   /
                                 |
                              sleep(2)
                                 |
                                x++
    }
  return 0;
}
```
Analisa: Output di atas menunjukkan bahwa aplikasi ini memanfaatkan sistem pemanggilan fork untuk menciptakan cabang-cabang proses. Tiap anak proses memiliki variabel "x" masing-masing yang independen dari yang lainnya.

3. fork03

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	childpid = fork();
	for (int i = 0; i < 5; i++) {
		cout << "This is process " << getpid() << endl;
		sleep(2);
	}
	return 0;
}

```

<img src="Week 7 UTS/image/3.png" alt="">

Visualisasi :

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
    loop 0 to 5 {             /     \
               pid: 7091, ppid: -    pid: 7092, ppid: 7091
               [Parent Process]     [Child Process]
                              \     /
                               \   /
                                 |
                              sleep(2)
                                 |
                                x++
    }
  return 0;
}
```

Analisa: Program di atas melakukan pengulangan proses forking, menghasilkan proses-proses baru dengan pesan yang mencatat ID unik dari setiap proses (PID). Kehadiran beberapa PID yang serupa menunjukkan bahwa proses induk melakukan forking beberapa kali, menciptakan proses-proses anak dengan PID yang sama.


4. fork04

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();
	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		cout << "My parent is " << getppid() << endl;
		/* keluar if akan menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid() << endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
		/* kode ini dieksekusi baik oleh proses parent dan child */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
		/* kode ini hanya dieksekusi oleh proses child */
		cout << "I am a child and I am quitting work now!"<< endl;
	}
	else {
		/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
	do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda bahwa proses child diterminasi */
		wait_result = wait(&status);
	} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}

```

<img src="Week 7 UTS/image/4.png" alt="">

Visualisasi : 

```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 7134, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                       wait          pid: 7135, ppid: 7134
                           \             [Child Process]
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```

Analisa: Program tersebut melakukan proses fork untuk menciptakan proses anak. Proses induk mencetak pesan yang menunjukkan identitasnya, yaitu "I am the parent and my pid = 7134", di mana 7134 adalah PID dari proses induk itu sendiri. Sementara proses anak mencetak pesan "My parent is 7134" diikuti dengan PID-nya sendiri, yaitu "I am a child and my pid = 7135". Keduanya kemudian mencetak pesan yang serupa. Proses anak kemudian memberikan pesan penutup "I am a child and I am quitting work now!" untuk menandakan berhentinya prosesnya. Proses induk menyusul dengan mencetak pesan "I am the parent and I am quitting".



5. fork05

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
  pid_t child_pid;
  int status; 
  pid_t wait_result;
  child_pid = fork();
  if (child_pid == 0) {
    /* kode ini hanya dieksekusi proses child */
    cout << "I am a child and my pid = " << getpid() << endl;
    execl("/bin/ls", "ls", "-l", "/home", NULL);
    /* jika execl berhasil kode ini tidak pernah digunakan */
    cout << "Could not execl file /bin/ls" << endl;
    exit(1);
    /* exit menghentikan hanya proses child */
   }
  else if (child_pid > 0) {
    /* kode ini hanya mengeksekusi proses parent */
   cout << "I am the parent and my pid = " << getpid() << endl;
   cout << "My child has pid = " << child_pid << endl;
  }
  else {
   cout << "The fork system call failed to create a new process" << endl;
   exit(1);
  }
  /* kode ini hanya dieksekusi oleh proses parent karena
  child mengeksekusi dari “/bin/ls” atau keluar */
   cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
   if (child_pid == 0) {
  /* kode ini tidak pernah dieksekusi */
   printf("This code will never be executed!\n");
  }
  else {
   /* kode ini hanya dieksekusi oleh proses parent */
    cout << "I am a parent and I am going to wait for my child" << endl;
    do {
      /* parent menunggu sinyal SIGCHLD mengirim tanda bila proses child diterminasi */
      wait_result = wait(&status);
    } while (wait_result != child_pid);
    cout << "I am a parent and I am quitting." << endl;
  }
  return 0;
}

```

<img src="Week 7 UTS/image/5.png" alt="">

Visualisasi : 


```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 7167, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                        |          pid: 7168, ppid: 7167
                       wait           total 20
                          \           execl(/bin/ls) 
                           \         [Child Process]
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```

Analisa: Program di bawah ini adalah sebuah contoh implementasi `fork()` dengan dua proses yang saling terhubung. Proses pertama memiliki ID proses (PID) 7167 dan ID proses induk (PPID) yang tidak diketahui pada awalnya, yang merujuk kepada proses utama (biasanya program utama atau induk). Ketika program dijalankan dan fungsi fork() dipanggil, akan tercipta proses baru dengan PID 7167 dan PPID 7168. Setelah itu, program induk akan mencetak output yang menampilkan nomor PID dan PID anak. Kemudian, program induk akan menunggu hingga proses anak selesai dieksekusi. Saat proses anak selesai dan mencetak output yang menampilkan nomor PID dan PID induknya, program induk akan segera keluar dari proses. Setelah proses anak selesai dieksekusi dan keluar dari proses, barulah program induk juga akan keluar dari prosesnya.


6. Fork06

```
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();


	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		execl("fork03", "goose", NULL);
		/* jika execl berhasil kode ini tidak pernah digunakan */
		cout << "Could not execl file fork3" << endl;
		exit(1);
		/* exit menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid()<< endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
	/* kode ini hanya dieksekusi oleh proses parent karena
	child mengeksekusi dari “fork3” atau keluar */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
	/* kode ini tidak pernah dieksekusi */
		printf("This code will never be executed!\n");
	}
	else {
	/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
		do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda
		bila proses child diterminasi */
			wait_result = wait(&status);
		} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}

```

<img src="Week 7 UTS/image/6.png" alt="">

Visualisasi : 


```
int main() { 
  fork();              > Child process created <
                                 +
                               /   \
                              /     \
               pid: 7242, ppid: -    \
                [Parent Process]      \  
                        |              \
                        |               \
                        |          pid: 7243, ppid: 7242
                       wait           execl(fork3) 
                          \           [Child Process]
                           \           /
                            \         /
                             \       /
                              \     /
                               \   /
                                 |
                                exit
    
  return 0;
}
```

Analisa: Proses induk mencetak pesan yang menyatakan identitasnya sebagai "I am the parent and my pid = 7242", di mana 7242 adalah PID dari proses induk itu sendiri. Sementara itu, proses anak mencetak pesan "My parent is 7242" diikuti dengan PID-nya sendiri, yaitu "I am a child and my pid = 7243". Keduanya juga mencetak pesan yang menunjukkan bahwa mereka adalah proses yang sehat dan bahagia dengan PID masing-masing. Kemudian, kedua proses terus mencetak pesan "This is process XXXX", di mana XXXX menunjukkan PID masing-masing proses, menunjukkan iterasi dalam siklus kerjanya. Akhirnya, proses induk mengakhiri eksekusinya dengan mencetak pesan "I am the parent and I am quitting.".


### Jawaban nomor 2

```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

#define ROWS 4
#define COLS 4

void printMatrix(int matrix[ROWS][COLS]) {
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int matrix[ROWS][COLS];
    int scalar = 2; // Skalar yang akan digunakan untuk perkalian

    // Menginisialisasi matriks
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            matrix[i][j] = i * j;
        }
    }

    // Menampilkan matriks awal
    printf("Matriks Awal:\n");
    printMatrix(matrix);

    // Proses fork
    pid_t pid = fork();

    // Menjalankan proses anak
    if (pid == 0) {
        // Melakukan perkalian matriks dengan skalar
        printf("\nProses Anak - Matriks Hasil:\n");
        for (int i = 0; i < ROWS; i++) {
            for (int j = 0; j < COLS; j++) {
                matrix[i][j] *= scalar;
                printf("%d ", matrix[i][j]);
            }
            printf("\n");
        }
    } else if (pid > 0) {
        // Menunggu proses anak selesai
        wait(NULL);
        printf("\nProses Induk Selesai.\n");
    } else {
        // Fork gagal
        fprintf(stderr, "Fork gagal.\n");
        return 1;
    }

    return 0;
}

```

Output : 

<img src="Week 7 UTS/image/7.png" alt="">

Analisa: Kode di atas merupakan sebuah program perkalian 2 matriks [4 x 4] dalam bahasa C yang menggunakan fork() untuk melakukan proses multiproses.

Fork Process: Setelah menginisialisasi matriks, program melakukan fork untuk menciptakan proses anak. Proses anak akan mengalikan setiap elemen matriks dengan skalar, sedangkan proses induk akan menunggu proses anak selesai.

Serial Processing: Meskipun perkalian skalar dilakukan secara paralel oleh proses anak, program menunggu proses anak selesai sebelum melanjutkan eksekusi. Ini dilakukan dengan menggunakan fungsi wait(), sehingga proses induk akan menunggu sampai proses anak selesai sebelum mencetak pesan bahwa proses induk telah selesai.
