INTEGRASI NUMERIK

Metode Recursive Trapezoid

Metode aturan trapesium adalah suatu teknik untuk mendekati integral yang pasti. Menurut teorema dasar rumus integral dapat dihitung dengan rumus seperti berikut:


$$
{\displaystyle \int _{a}^{b}f(x)\,dx=F(b)-F(a)}
$$


Dengan *F(x)* adalah antiderivatif *f(x)* (yakni *F’(x)=f(x)*).  Banyak integral tentu yang dapat dihitung dengan rumus tesebut, namun  demikian, tidak sedikit integral tentu yang tidak dapat dihitung dengan  rumus di atas, hal itu dikarenakan integral *f(x)* tidak mempunyai  antiderivatif yang dapat dinyatakan dalam fungsi-fungsi elementer. Dalam  hal ini perhitungan yang dapat dilakukan adalah secara numerik. 

Integrasi numerik merupakan suatu alat utama yang digunakan para ilmuwan untuk mendapatkan nilai-nilai hampiran untuk integral tentu yang tidak  dapat diselesaikan secara analitik. Dalam mendapatkan nilai-nilai  hampiran integral tentu digunakan banyak metode, salah satu metode yang  dapat digunakan adalah Aturan Trapesium Rekursif. Berikut akan  dijelaskan penghitungan integral tentu menggunakan Aturan Trapesium  Rekursif. 

**Aturan Trapesium Rekursif**

Aturan trapesium bekerja dengan cara mendekati daerah bawah grafik fungsi f(x) sebagai trapesium dan menghitung luas daerah yang terasir. Aturan trapesium juga dapat dikatakan sebagai hasil yang diperoleh dari rata-rata jumlah Reimann kiri dan kanan. Pendekatan integral lebih baik dilakukan dengan mempartisi inerval integrasi dan menerapkan aturan trapesium untuk setiap subinterval dan kemudian menjumlahkan hasilnya.

Estimasi berdasarkan 1 interval :
$$
h=b-a
$$

$$
R(0,0) = \frac{b-a}{2}(f(a)+f(b))
$$

Estimasi berdasarkan 2 interval :
$$
h = \frac{b-a}{2}
$$

$$
R(1,0) = \frac{b-a}{2}\left [(f(a+h)+\frac{1}{2}(f(a)+f(b)) \right ]
$$

$$
R(1,0) = \frac{1}{2}R(0,0)+h[f(a+h)]
$$



**Metode Trapesium Rekursif**
$$
R(0,0) = \frac{b-a}{2}[f(a)+f(b)]
$$

$$
R(n,0) = \frac{1}{2}R(n-1,0)+h \left [ \sum _{k=1}^{2(n-1)}f(a+(2k-1)h)\right ]
$$



**Algoritma Integral Trapezoid**

1. Definisikan *$y=f(x)$*
2. Tentukan batas bawah (a) dan batas atas integrasi (b)
3. Tentukan jumlah pembagi n
4. Hitung *$h=\frac{(b-a)}{2^n}$*
5. Hitung *$L = \frac{h}{2}\left (f_{0}+2\sum_{i=1}^{n-1}f_{i}+f_{n} \right )$*



**Code**

```python
def fungsi (x) :
    y = 1/(1+x)
    return y

print("f(x) = 1/(1+x)")
a = float(input("Masukkan batas bawah integral : "))
b = float(input("Masukkan batas atas integral : "))
c = int(input("masukkan n : "))
eror = []

for iterasi in range (0,c):
    n=2**iterasi
    h=(b-a)/n

    xi = a
    y = 0
    for i in range(1,n):
        xi = xi+h
        y += fungsi(xi)
    hasil = (h)*((fungsi(a)+(2*y)+fungsi(b))/2)
    eror.append(hasil)
    print ('iterasi ke-',iterasi+1,"n:",n,'hasil =',hasil)
print (eror[iterasi-1])
print(eror[iterasi])
akhir = (eror[iterasi-1]-eror[iterasi])
print(akhir)
print ("estimasi error : "+str(akhir))

```



**Output:**

```python
f(x) = 1/(1+x)
Masukkan batas bawah integral : 2
Masukkan batas atas integral : 6
masukkan n : 8
iterasi ke- 1 n: 1 hasil = 0.9523809523809523
iterasi ke- 2 n: 2 hasil = 0.8761904761904762
iterasi ke- 3 n: 4 hasil = 0.8547619047619047
iterasi ke- 4 n: 8 hasil = 0.8491813741813743
iterasi ke- 5 n: 16 hasil = 0.8477698845652135
iterasi ke- 6 n: 32 hasil = 0.847415938934486
iterasi ke- 7 n: 64 hasil = 0.8473273845698198
iterasi ke- 8 n: 128 hasil = 0.8473052417171961
0.8473273845698198
0.8473052417171961
2.214285262369664e-05
estimasi error : 2.214285262369664e-05
```

