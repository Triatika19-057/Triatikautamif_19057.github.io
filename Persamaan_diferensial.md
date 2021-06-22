### Persamaan diferensial 

Persamaan diferensial adalah suatu persamaan yang memuat satu atau lebih turunan fungsi yang tidak diketahui. Persamaan diferensial biasa dikatakan linear, apabila persamaan diferensial tersebut mempunyai peubah tak bebas maupun turunannya bersifat linear.
$$
dx/
dy
​
 +5x−5=0   
$$

$$
dx 
2
 /
d 
2
 y
​
 +6x+7=0
$$

Bentuk umum PDBL orde-n adalah sebagai berikut an (x) yn + an-1 (x) yn-1 + … + a0 (x) y = f(x) dengan an(x)  0 dan an (x), an-1 (x), … , a0 (x) adalah koefisien PD.

Bila f(x) = 0 disebut PDBL Homogen, sebaliknya jika tidak disebut PDBL tak homogen.

Orde PDB adalah turunan tertinggi yang terlibat dalam PDB.

Persamaan diferensial di mana y sebagai peubah tak bebas yang bergantung pada peubah bebas x atau suatu fungsi y = f(x) disebut solusi PDB jika fungsi y = f(x) disubtitusikan ke PDB diperoleh persamaan identitas.

##### Metode Euler

Definisi

metode euler adalah metode yang diturunkan dari derettaylor dan digunakan untuk menyelesaikan persamaan differensial.

##### Algoritma

- Algoritma Metode Euler

- Menentukan letak integrasi pertama dari x dan y

- Menentukan banyak iterasi dan ukuran yang akan digunakan

- Melakukan integrasi menggunakan persamaan

  kode:

```
import numpy as np
import matplotlib.pyplot as plt

def f(x,y):
    f = -0.05*(y-20)
    return f

def analytic(x):
    k = 0.05
    y = 95
    ff = 20 + (y-20)*np.exp(-k*x)
    return ff

x0 = 0
y0 = 95
xf = 100
n = 30
h = (xf-x0)/(n-1)
x = np.linspace(x0,xf,n)
y = np.zeros((n,1))
y[0] = y0

na = 100
xx = np.linspace(x0,xf,na)
yy = np.zeros((na,1))
yy[0] = y0

for i in range(1,n):
    y[i] = y[i-1]+h*f(x[i-1],y[i-1])

for j in range(0,na):
    yy[j] =(analytic(xx[j]))

p1 = plt.plot(x,y,'x')
p2 = plt.plot(xx,yy,'-')
plt.title('Hukum Pendinginan Newton')
plt.xlabel("Waktu(Menit)")
plt.ylabel("Suhu($^o$C)")
plt.legend( (p1[0], p2[0]), ('Metode Euler', 'Analitis') )
plt.show()
```

