# Scheduling Algorithms - Tugas Pertemuan 13 (20 Mei 2025)

NAMA : Firda Rahayu

NRP : 3124521002

KELAS : 1 IT A

## 1.SJF without arrival time (non-preemptive)

### Kode Program:

---
```
#include<stdio.h>
struct proc
{
    int no,bt,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    return p;
}
int main()
{
    struct proc p[10],tmp;
    float avgtat=0,avgwt=0;
    int n,ct=0;
    printf("<--SJF Scheduling Algorithm Without Arrival Time (Non-Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)    
            if(p[j].bt>p[j+1].bt)
            {
				tmp=p[j];
				p[j]=p[j+1];
				p[j+1]=tmp;
            }
    printf("\nProcessNo\tBT\tCT\tTAT\tWT\tRT\n");
    for(int i=0;i<n;i++)
    {
        ct+=p[i].bt;
		p[i].ct=p[i].tat=ct;
		avgtat+=p[i].tat;
        p[i].wt=p[i].tat-p[i].bt;
        avgwt+=p[i].wt;
        printf("P%d\t\t%d\t%d\t%d\t%d\t%d\n",p[i].no,p[i].bt,p[i].ct,p[i].tat,p[i].wt,p[i].wt);
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}

```

### Output :
![Gambar teks editor VS Code](img/output1.jpeg)

![Gambar teks editor VS Code](img/g1.jpeg)

```mermaid
gantt
    dateFormat  X
    axisFormat %s
    section Processes
    P3:0,2
    P1:2,5
    P5:5,11
    P2:11,18
    P4:18,27
```

analisa : Program C ini mensimulasikan algoritma penjadwalan Shortest Job First (SJF) secara non-preemptive, dengan asumsi semua proses tiba pada waktu nol. Program dimulai dengan mendefinisikan struktur proc untuk menyimpan detail proses seperti nomor, waktu burst (bt), waktu selesai (ct), waktu penyelesaian (tat), dan waktu tunggu (wt). Fungsi read bertanggung jawab untuk mengambil input waktu burst untuk setiap proses secara interaktif. Dalam fungsi main, setelah mendapatkan jumlah total proses, program membaca waktu burst untuk setiap proses. Selanjutnya, program mengimplementasikan algoritma bubble sort untuk mengatur proses dalam urutan menaik berdasarkan waktu burst mereka. Setelah pengurutan ini, program mengulang melalui proses yang telah diurutkan untuk menghitung waktu selesai, waktu penyelesaian (yang sama dengan waktu selesai karena waktu kedatangan adalah 0), dan waktu tunggu mereka. Terakhir, program mencetak tabel yang merangkum metrik ini untuk setiap proses dan menghitung serta menampilkan rata-rata waktu penyelesaian dan rata-rata waktu tunggu untuk semua proses.

## 2.SJF with arrival time (non-prremptive)

### Kode Program:

---
```
#include<stdio.h>
struct proc
{
    int no,at,bt,it,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    return p;
}
int main()
{
    int  n,j,min=0;
    float avgtat=0,avgwt=0;
    struct proc p[10],temp;
    printf("<--SJF Scheduling Algorithm (Non-Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    for(j=1;j<n&&p[j].at==p[0].at;j++)
        if(p[j].bt<p[min].bt)
            min=j;
    temp=p[0];
    p[0]=p[min];
    p[min]=temp;
    p[0].it=p[0].at;
    p[0].ct=p[0].it+p[0].bt;
    for(int i=1;i<n;i++)
    {
        for(j=i+1,min=i;j<n&&p[j].at<=p[i-1].ct;j++)
            if(p[j].bt<p[min].bt)
                min=j;
        temp=p[i];
        p[i]=p[min];
        p[min]=temp;
        if(p[i].at<=p[i-1].ct)
            p[i].it=p[i-1].ct;
        else
            p[i].it=p[i].at;
        p[i].ct=p[i].it+p[i].bt;
    }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\tRT\n");
    for(int i=0;i<n;i++)
    {
        p[i].tat=p[i].ct-p[i].at;
        avgtat+=p[i].tat;
        p[i].wt=p[i].tat-p[i].bt;
        avgwt+=p[i].wt;
        printf("P%d\t\t%d\t%d\t%d\t%d\t%d\t%d\n",p[i].no,p[i].at,p[i].bt,p[i].ct,p[i].tat,p[i].wt,p[i].wt);
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}

```

### output :
![Gambar teks editor VS Code](img/output2.jpeg)

![Gambar teks editor VS Code](img/g2.jpeg)

```mermaid
gantt
    dateFormat  X
    axisFormat %s
    section Processes
    P2:2,5
    P3:5,12
    P1:12,16
```

analisa :  Program C ini mensimulasikan algoritma penjadwalan Shortest Job First (SJF) non-preemptive, secara eksplisit menggabungkan waktu kedatangan proses untuk menentukan urutan eksekusi. Program dimulai dengan mendefinisikan struktur proc untuk menyimpan detail setiap proses, termasuk nomor, waktu kedatangan (at), waktu burst (bt), waktu mulai awal (it), waktu selesai (ct), waktu penyelesaian (tat), dan waktu tunggu (wt). Setelah mengumpulkan jumlah proses serta waktu kedatangan dan waktu burst masing-masing dari pengguna, program awalnya mengurutkan semua proses berdasarkan waktu kedatangan mereka. Selanjutnya, program memastikan bahwa di antara proses yang tiba secara bersamaan pada waktu paling awal, proses dengan waktu burst terpendek dijadwalkan terlebih dahulu. Lingkaran penjadwalan utama kemudian secara iteratif memilih pekerjaan terpendek dari kumpulan proses yang telah tiba pada waktu penyelesaian proses yang dieksekusi sebelumnya. Untuk setiap proses yang dipilih, waktu eksekusi awalnya dihitung, memperhitungkan potensi waktu idle CPU jika proses tiba setelah yang sebelumnya selesai. Setelah ini, program menghitung waktu selesai, waktu penyelesaian (waktu selesai dikurangi waktu kedatangan), dan waktu tunggu (waktu penyelesaian dikurangi waktu burst) untuk setiap proses. Terakhir, program menyajikan tabel komprehensif yang merangkum metrik ini untuk semua proses dan menghitung rata-rata waktu penyelesaian keseluruhan dan rata-rata waktu tunggu, memberikan simulasi lengkap algoritma SJF non-preemptive dengan waktu kedatangan dinamis.

## 3.SRTF (preemptive) contoh kasus sesuaikan dengan PPT

### Kode Program:
---
```
#include<stdio.h>
#define MAX 9999
struct proc
{
    int no,at,bt,rt,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    p.rt=p.bt;
    return p;
}
int main()
{
    struct proc p[10],temp;
    float avgtat=0,avgwt=0;
    int n,s,remain=0,time;
    printf("<--SRTF Scheduling Algorithm (Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\n");
    p[9].rt=MAX;
    for(time=0;remain!=n;time++)
    {
        s=9;
        for(int i=0;i<n;i++)
            if(p[i].at<=time&&p[i].rt<p[s].rt&&p[i].rt>0)
                s=i;
        p[s].rt--;
        if(p[s].rt==0)
        {
            remain++;
            p[s].ct=time+1;
            p[s].tat=p[s].ct-p[s].at;
            avgtat+=p[s].tat;
            p[s].wt=p[s].tat-p[s].bt;
            avgwt+=p[s].wt;
            printf("P%d\t\t%d\t%d\t%d\t%d\t%d\n",p[s].no,p[s].at,p[s].bt,p[s].ct,p[s].tat,p[s].wt);
        }
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}

```
### Output :
![Gambar teks editor VS Code](img/output3.jpeg)

```mermaid
gantt
    dateFormat  X
    axisFormat %s
    section Processes
    P1:0,1
    P2:1,5
    P4:5,10
    P1:10,17
    P3:17,26
```

analisa : Program C ini dengan cermat mensimulasikan algoritma penjadwalan Shortest Remaining Time First (SRTF), yang merupakan varian preemptive dari Shortest Job First, dengan secara eksplisit menggabungkan waktu kedatangan proses. Program mendefinisikan struktur proc untuk menyimpan nomor proses, waktu kedatangan, total waktu burst, sisa waktu burst, waktu selesai, waktu penyelesaian, dan waktu tunggu, menginisialisasi sisa waktu dengan waktu burst. Setelah mengumpulkan jumlah proses serta waktu kedatangan dan waktu burst masing-masing dari pengguna, proses awalnya diurutkan berdasarkan waktu kedatangan mereka. Inti dari logika SRTF diimplementasikan dalam loop berbasis waktu yang mensimulasikan eksekusi CPU. Di setiap unit waktu, program secara dinamis mengidentifikasi proses yang telah tiba dan saat ini memiliki sisa waktu burst terpendek di antara semua proses yang tersedia. Proses yang dipilih ini kemudian diizinkan untuk dieksekusi selama satu unit waktu, mengurangi sisa waktu burst-nya. Mekanisme evaluasi ulang dan pemilihan yang berkelanjutan ini secara inheren mengimplementasikan preemption, memungkinkan CPU untuk beralih ke proses yang baru tiba atau yang tersedia saat ini jika sisa waktunya lebih pendek daripada yang sedang berjalan. Ketika sebuah proses selesai dieksekusi (sisa waktunya menjadi nol), waktu penyelesaiannya dicatat, dan waktu penyelesaian serta waktu tunggunya dihitung dan diakumulasikan untuk rata-rata keseluruhan. Terakhir, program menampilkan tabel terperinci yang menunjukkan metrik ini untuk setiap proses dan menyajikan rata-rata waktu penyelesaian dan rata-rata waktu tunggu yang dihitung untuk seluruh kumpulan proses.





