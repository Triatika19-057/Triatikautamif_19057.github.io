# Persamaan linear

**Persamaan linear** adalah sebuah **persamaan** aljabar, yang tiap sukunya mengandung konstanta, atau perkalian konstanta dengan variabel tunggal. **Persamaan** ini dikatakan **linear** sebab hubungan matematis ini dapat digambarkan sebagai garis lurus dalam Sistem koordinat Kartesius.

Jika terdapat lebih dari satu persamaan linear, maka persamaan linear tersebut akan menjadi sebuah sistem. Bentuk umum sistem persamaan linear adalah sebagai berikut:
$$
a 
11
​
 x 
1
​
 +a 
12
​
 x 
2
​
 +a 
13
​
 x 
3
​
 …+a 
1n
​
 x 
n
​
 =C1
$$

$$
a 
21
​
 x 
1
​
 +a 
22
​
 x 
2
​
 +a 
23
​
 x 
3
​
 +…⋅a 
2n
​
 x 
n
​
 =c 
2
​
$$

$$
a 
n1
​
 x 
1
​
 +a 
n2
​
 x 
2
​
 +a 
n3
​
 …+a 
nn
​
 x 
n
​
 =Cn
$$

Setelah memahami apa itu persamaan linear, akan kita bahas beberapa macam sistem persamaan linear.

## **Sistem Persamaan Linear Satu Variabel**

Sistem persamaan linear satu variabel adalah sistem persamaan dengan hanya terdapat sebuah variabel saja berpangkat 1. Bentuk umumnya sebagai berikut:
$$
ax + b = 0
$$
dengan a dan b adalah bilangan bulat bukan nol dan b konstanta.

## **Sistem Persamaan Linear Dua Variabel**

Berbeda dari sebelumnya, sistem persamaan linear dua variabel adalah sistem persamaan dengan variabel berjumlah dua berpangkat 1 satu. Bentuk umumnya sebagai berikut:
$$
ax + by = c
$$
dengan a dan b adalah bilangan bulat bukan nol dengan c adalah konstanta.

## **Sistem Persamaan Linear Tiga Variabel**

Sistem persamaan linear tiga variabel merupakan sistem persamaan dengan variabel berjumlah tiga berpangkat 1 satu. Bentuk umumnya sebagai berikut:
$$
ax + by + cz = d
$$
dengan a, b, dan c adalah bilangan bulat bukan nol dengan d adalah konstanta.

### Eliminasi gauss

Eliminasi Gauss adalah suatu metode untuk mengoperasikan nilai-nilai di dalam matriks sehingga menjadi matriks yang lebih sederhana lagi. Dengan melakukan operasi baris sehingga matriks tersebut menjadi matriks yang baris. Ini dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks. Caranya dengan mengubah persamaan linear tersebut ke dalam matriks teraugmentasi dan mengoperasikannya. Setelah menjadi matriks baris, lakukan substitusi balik untuk mendapatkan nilai dari variabel-variabel tersebut.

Ciri ciri Metode Gauss adalah 

1. ![img](http://1.bp.blogspot.com/-V0k8dw-1jfA/Uz4xySaYx1I/AAAAAAAAAI0/IZTXbstKlsc/s1600/gaus.PNG)

2. Jika suatu baris tidak semua nol, maka bilangan pertama yang tidak nol adalah 1 (1 utama)
3. Baris nol terletak paling bawah 
4. 1 utama baris berikutnya berada dikanan 1 utama baris diatasnya
5. Dibawah 1 utama harus nol

#### Algoritma

Metode gauss merupakan metode yang terdiri dari dua langkah yaitu eliminasi maju dan subtitusi mundur

#### Penjelasan

Pertama kita tanyakan dulu matriks 2D dengan panjang dan lebar berapa yang akan diproses sekaligus nilai tiap sel matriksnya

```
n = int(input("Berapa variabel? "))
mtx = [[float(input("Nilai untuk [{}][{}]=".format(i,j))) for j in range(n+1)] for i in range(n)]
```

lanjut untuk memproses matriknya, disini metode gauss memproses dengan cara membuat nilai matriks diagonal bernilai 1 dan sel lainnya bernilai 0

[1,0,00,1,00,0,1]=[xyz]

untuk mendapatkan hasil seperti itu maka diperlukan looping di setiap array dalam array (multidimensi) karena bentuk dari matriks tersebut jika di tampilkan dalam program adalah

```
[
    [1,0,0],
    [0,1,0],
    [0,0,1]
]
```

###### Eliminasi Jordan

Eliminasi Gauss-Jordan adalah pengembangan dari eliminasi Gauss yang hasilnya lebih sederhana lagi. Caranya adalah dengan meneruskan operasi baris dari eliminasi Gauss sehingga menghasilkan matriks yang Eselon-baris. Ini juga dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks.

[![img](http://3.bp.blogspot.com/-3t1sgBIIpgM/Uz4v58p53yI/AAAAAAAAAIY/x-10CNKNC5M/s1600/metgaus.PNG)](http://3.bp.blogspot.com/-3t1sgBIIpgM/Uz4v58p53yI/AAAAAAAAAIY/x-10CNKNC5M/s1600/metgaus.PNG)

metode ini digunakan untuk mencari invers dari sebuah matriks.

Prosedur umum untuk metode eliminasi Gauss-Jordan ini adalah

1. Ubah sistem persamaan linier yang ingin dihitung menjadi matriks augmentasi.

2. Lakukan operasi baris elementer pada matriks augmentasi (A|b) untuk mengubah matriks A menjadi dalam bentuk baris eselon yang tereduksi

   kode:

```
import numpy as np
import sys

n = int(input('Jumlah Variabel: '))
a = np.zeros((n,n+1))
x = np.zeros(n)

print('Masukkan Data Matriks:')
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input( 'a['+str(i)+']['+ str(j)+']= '))
print ('\nMatriks :')
print (a)

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')

    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]

        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]

    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]

    x[i] = x[i]/a[i][i]

print('\nNilai Variabel: ')
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = '\t')
```

