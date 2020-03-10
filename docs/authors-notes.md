# Pendekatan Deret MacLaurin

*DERET MacLaurin* adalah Suatu fungsi f(x) yang memiliki turunan *f'(x), f''(x), f'''(x)* dan seterusnya yang kontinyu dalam interval I dengan *a, x I* maka untuk *x* disekitar *a* yaitu *|x-a|<*R , *f(x)* dapat diekspansi kedalam Deret Taylor.

Dalam kasus khusus jika *a=0*, maka disebut *Deret MacLaurin* atau sering disebut Deret Taylor baku. Dan didefinisikan sebagai berikut 

Definisi :
$$
f(x)=f(0)+f’(0)x \displaystyle+\frac{{{f}\text{'}\text{'}{\left({0}\right)}}}{{{2}!}}{x}^{2}
\displaystyle+\frac{{{f}\text{'}\text{'}\text{'}{\left({0}\right)}}}{{{3}!}}{x}^{3}
\displaystyle+\ldots
\displaystyle+\frac{{{{f}^{{\text{n}}}{\left({0}\right)}}}}{{{n}!}}{x}^{n}
$$
Atau bisa dinyatakan dengan:
$$
f(x)=\sum_{n=0}^\infty \frac{f^{(n)}n(0)}{n!}x^{n}
$$
Deret MacLaurin sangat bermanfaat dalam metode numerik untuk menghitung atau menghampiri nilai-nilai fungsi yang sudah dihitung secara manual seperti nilai *sin x, cos x*, . 

## Tugas

Hitunglah e^2x untuk nilai x=4, kemudian expensikan hingga selisih yang dihasilkan kurang dari nilai error yang ditentukan yaitu e < 0,001.

### Penyelesaian

Fungsi awal exponen :
$$
f(x) = e^{2x}\ 
$$
Dapat juga didefinisikan dengan rumus   : 
$$
e^{2x} = \sum_{n=0}^\infty \frac{(2x)^n}{n!} = \sum_{n=0}^\infty (2)^n\frac{x^n}{n!}
$$
Tabel perhitungan untuk turunan exponensial  :
$$
\begin{array}{|c|c|l|}
\hline f(x) & e^{2 x} & f(0)=1 \\
\hline f^{\prime}(x) & 2 e^{2 x} & f^{\prime}(0)=2 \\
\hline f^{\prime \prime}(x) & 4 e^{2 x} & f^{\prime \prime}(0)=4 \\
\hline f^{\prime \prime \prime}(x) & 8 e^{2 x} & f^{\prime \prime \prime}(0)=8 \\
\hline f^{\prime \prime \prime \prime}(x) & 16 e^{2 x} & f^{\prime \prime \prime \prime}(0)=16 \\
\hline
\end{array}
$$
Berikut adalah penyelesaian untuk mencari nilai expansi :
$$
f(x)=f(0)+\frac{f^{\prime}(0)}{1 !} x+\frac{f^{\prime \prime}(0)}{2 !} x^{2}+\frac{f^{\prime \prime \prime}(0)}{3 !} x^{3}+\frac{f^{\prime \prime \prime \prime}(0)}{4 !} x^{4} + ...
$$
nilai turunan pada tabel dimasukkan kedalam rumus sehingga didapatkan seperti ini :
$$
f(x)=1+\frac{2}{1 !} x+\frac{4}{2 !} x^{2}+\frac{8}{3 !} x^{3}+\frac{16}{4 !} x^{4} + ...
$$
kemudian, nilai x diganti dengan 4 :
$$
f(x)=1+\frac{2}{1 !} 4+\frac{4}{2 !} 4^{2}+\frac{8}{3 !} 4^{3}+\frac{16}{4 !} 4^{4} + ...
$$
perhitungan diatas akan terus berulang hingga nilai selisih mendekati nilai error yang ditentukan yaitu kurang dari 0,001

### Listing Program

**Script**

```python
import math

error = 0.001

def f(x):
    f_turunan = 1
    current=i=0
    iteration = True
    while iteration:
        old= current
        current += (f_turunan*(x**i))/math.factorial(i)
        print('f ke-', i,'=', 'Ea=', current-old )
        if current-old < error:
            iteration = False

        else:
            f_turunan *=2
            i +=1

f(4)

```

**Output**

```python
f ke- 0 = Ea= 1.0
f ke- 1 = Ea= 8.0
f ke- 2 = Ea= 32.0
f ke- 3 = Ea= 85.33333333333333
f ke- 4 = Ea= 170.66666666666669
f ke- 5 = Ea= 273.0666666666666
f ke- 6 = Ea= 364.08888888888896
f ke- 7 = Ea= 416.1015873015872
f ke- 8 = Ea= 416.1015873015872
f ke- 9 = Ea= 369.8680776014112
f ke- 10 = Ea= 295.89446208112895
f ke- 11 = Ea= 215.195972422639
f ke- 12 = Ea= 143.46398161509296
f ke- 13 = Ea= 88.28552714774924
f ke- 14 = Ea= 50.448872655856576
f ke- 15 = Ea= 26.90606541645684
f ke- 16 = Ea= 13.45303270822842
f ke- 17 = Ea= 6.330838921519444
f ke- 18 = Ea= 2.8137061873417224
f ke- 19 = Ea= 1.184718394670199
f ke- 20 = Ea= 0.47388735786807956
f ke- 21 = Ea= 0.18052851728316455
f ke- 22 = Ea= 0.06564673355751438
f ke- 23 = Ea= 0.022833646454728296
f ke- 24 = Ea= 0.0076112154847578495
f ke- 25 = Ea= 0.0024355889549951826
f ke- 26 = Ea= 0.0007494119863622473
```



