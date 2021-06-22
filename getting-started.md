**DEFINISI TURUNAN**

Turunan merupakan suatu perhitungan terhadap perubahan nilai fungsi karena perubahan nilai input (variabel).

Turunan dapat disebut juga sebagai diferensial dan proses dalam menentukan turunan suatu fungsi disebut sebagai diferensiasi.
$$
f'\left( x\right) =\cdot \lim _{h\rightarrow 0}\dfrac{f\left( x+h\right) -f\left( x\right) }{h}
$$
**Berikut merupakan beberapa penerapan turunan.**

- Turunan dapat diterapkan untuk menghitung gradien dari garis singgung suatu kurva.
- Turunan dapat digunakan untuk menentukan interval dimana suatu fungsi naik atau turun.
- Turunan dapat diterapkan untuk menentukan nilai stasioner suatu fungsi.
- Turunan dapat diterapkan dalam menyelesaikan permasalahan yang berkaitan dengan persamaaan gerak.
- Turunan dapat digunakan untuk menyelesaikan permasalahan maksimum-minimum.

**DEFINISI TURUNAN NUMERIK**

turunan numerik a menentukan hampiran nilai turunan fungsi f yang diberikan dalam bentuk tabel. 

**Tiga pendekatan dalam menghitung turunan numerik:** 

​	      1 . Hampiran selisih maju 
$$
\begin{aligned}f\left( x_{0}\right) =\dfrac{f\left( x_{0}+h\right) -f\left( x_{0}\right) }{h}\dfrac{=f_{1}-f_{2}}{h}\\ .\end{aligned}
$$
​		  2. Hampiran selisih mundur 

​		  
$$
f\left( x0\right) =\dfrac{f\left( x_{0}\right) -f\left( x_{0}-h\right) }{h}=\dfrac{f_{0}-f_{1}}{h}
$$


​		 3. Hampiran selisih pusat
$$
f\left( x_{0}\right) =\dfrac{f\left( x_{0}\right) -f\left( x_{0}-h\right) }{2h}=\dfrac{f\dfrac{}{1}f_{-1}}{2h}
$$
**Rumus-rumus turunan numerik untuk ketiga pendekatan tersebut dapat diturunkan dengan dua cara, yaitu:** 

1. Dengan bantuan deret Taylor 
2. Dengan hampiran polinom interpolasi

```
#1. Cetak Judul

#2. Definisikan f(x,y) = ½ x – ½ y

def f(x,y):

    o=0.5*x-0.5*y

    return o

#3. Definisikan turunan f(x,y)

    def deriv(x,y):

        h=0.000001

        z=round(((f(x+h,y)-f(x,y))/h)+(f(x,y)*(((f(x,y+h)-f(x,y))/h))),4)

        return z

#4. Definisikan faktorial

        def fakt(p):

            faktor=1

            for i in range (p):

​               i=i+1

​               faktor=faktor*i

               return faktor

#5. Inisiasi y=1

#6. Inisiasi x=0

#7. Input x yang ingin dicari

#8. Input nilai h

#9. while h<=x1:

                a=f(x,y)

                aa=f(h,y)

                c=deriv(x,y)

                cc=deriv(h,y)

                d=(c*a)

                dd=(cc*aa)

                ee=(dd*aa)

                e=(d*a)

                kk=[]

                kk.append(a)

                kk.append©

                kk.append(d)

                kk.append(e)

                jumlah=0

                galat=((h)*(len(kk))(ee-kk[3]))/fakt(len(kk)+1)

                g=h

                for i in range (len(kk)):

                    dd=float(kk[i]*g/fakt(i+1))

                    jumlah+=dd

                    g=g*h

                    hasil=jumlah+y+galat

                    h+=h

#10. Cetak nilai galat

#11. Cetak Hasil*Algoritma:*
```

```
def f(x,y):
    o=0.5*x-0.5*y
    return o
def deriv(x,y):
    h=0.00001
    z*round(((f(x+h, y)-f(x,y))/h) + (f(x,y) *(((f(x,y+h)-f(x,y))/h))),4)
    return z
#def derivi(x,y):
#    h = 0.00001
#    m*(((f(x+h, y)-f(x,y))/h),4)
#    return m
def fakt(p):
    for i in range(p):
        i= i+1
        faktor = faktor*i
    return faktor
y = 1
x = 0
x1 = float(input("masukan nilai x yang dicari: "))
h= float(input("masukan nilai h: "))
while h <= x1:
    a=f(x,y)
    aa = f(h,y)
    c=deriv(x,y)
    cc= deriv(h,y)
    d = (c*a)
    dd = (cc*aa)
    ee = (dd*aa)
    e = (d*a)
    kk = []
    kk.append(a)
    kk.append(c)
    kk.append(d)
    kk.append(e)
    jumlah = 0
    galat = ((h) **(len(kk))*(ee-k[3]))/fakt(len(kk)+1)
    g=h
    for i in range (len(kk)):
        dd= float(kk[i]*g/fakt(i+1))
        jumlah += dd
        g=g*h
    hasil = jumlah+y+galat
    h+=h
print("galat nya adalah : ", galat)
print("hasil nya adalah : ", hasil)
```

