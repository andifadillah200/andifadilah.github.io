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

print("iterasi","n","trapesium")
for iterasi in range (1,16,1):
    n=2*iterasi
    h=(b-a)/n

    xi = a
    y = 0
    for i in range(1,n):
        xi = xi+h
        y += fungsi(xi)
    hasil = (h)*((fungsi(a)+(2*y)+fungsi(b))/2)

    print (iterasi,n,hasil)

```



**Output:**

```python
f(x) = 1/(1+x)
Masukkan batas bawah integral : 5
Masukkan batas atas integral : 23
iterasi n trapesium
1 2 1.5375
2 4 1.428090659340659
3 6 1.4053571428571427
4 8 1.3971262491036611
5 10 1.3932610298649446
6 12 1.3911456598956602
7 14 1.389864598362667
8 16 1.3890308500940944
9 18 1.3884581777535068
10 20 1.388048015512552
11 22 1.3877442535422602
12 24 1.3875130525793768
13 26 1.3873330247622349
14 28 1.3871901162774283
15 30 1.387074784968122
```

