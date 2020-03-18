**Metode Gauss Jordan, Iterasi Jacobi, dan Gauss Seidel**

**Eliminasi Gauss Jordan**

Eliminasi gauss adalah suatu metode untuk mengoperasikan nilai-nilai di dalam matriks sehingga menjadi matriks yang lebih sederhana lagi. Dengan melakukan operasi baris sehingga matriks tersebut menjadi matriks yang baris. Ini dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks. Caranya dengan mengubah persamaan linear tersebut ke dalam matriks teraugmentasi dan mengoperasikannya. Setelah menjadi matriks baris, lakukan substitusi balik untuk mendapatkan nilai dari variabel-variabel tersebut.

Sedangkan, eliminasi gauss-jordan adalah pengembangan dari eliminasi gauss yang hasilnya lebih sederhana lagi. Caranya adalah dengan meneruskan operasi baris dari eliminasi gauss sehingga menghasilkan matriks yang eselon-baris. Ini juga dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks. Metode ini digunakan untuk mencari invers dari sebuah matriks.

Prosedur umum untuk metode eliminasi gauss-jordan ini adalah:

1. Ubah sistem persamaan linier yang ingin dihitung menjadi matriks augmentasi.

2. Lakukan operasi baris elementer pada matriks augmentasi (A|b) untuk mengubah matriks.

   Adapun formula untuk eliminasi maju (*Forward Elimination*) sebagai berikut:
   $$
   a_{ij} = a_{ij}-(\frac {a_ik}{a_kk}) a_{kj}   dimana  (k<=j<=n)
   $$
   

$$
x_{n-2} = \frac{b_{n-2}-a_{n-2,n}x_{n}-a_{n-2,n-1}x_{n-1}}{a_{n-2,n-2}}
$$

$$
................................
$$

$$
x_{i}=\frac{b_{i}-\sum_{j=i+1}^{n} a_{i.j}x_{j}}{a_i,j}
$$

**Source Code**

```phyton
import numpy as np

#Definisi Matrix
A = []
B = []

n = int(input("Masukkan ordo Matrix: "))
for i in range(n):
    baris=[]
    for i in range(n):
        a=int(input("Masukkan Nilai: "))
        baris.append(a)
    A.append(baris)
for i in range(n):
    h = int(input("Masukkan Hasil: "))
    B.append(h)

Matrix=np.array(A,float)
Hasil=np.array(B,float)

n=len(Matrix)


#Eliminasi Gauss

for k in range(0,n-1):
    for i in range(k+1,n):
        if Matrix[i,k]!=0 :
            lam=Matrix[i,k]/Matrix[k,k]
            Matrix[i,k:n]=Matrix[i,k:n]-(Matrix[k,k:n]*lam)
            Hasil[i]=Hasil[i]-(Hasil[k]*lam)

print("Matrix A : ",'\n',Matrix)

#Subtitution
x=np.zeros(n,float)
for m in range(n-1,-1,-1):
    x[m]=(Hasil[m]-np.dot(Matrix[m, m+1:n], x[m+1:n]))/Matrix[m,m]
    print('Nilai X ',m+1, '=',x[m])
```

**Output:**

```phyton
Masukkan ordo Matrix: 3

Masukkan Nilai: 1

Masukkan Nilai: -1

Masukkan Nilai: 4

Masukkan Nilai: 1

Masukkan Nilai: 4

Masukkan Nilai: 2

Masukkan Nilai: 3

Masukkan Nilai: 4

Masukkan Nilai: 2

Masukkan Hasil: 12

Masukkan Hasil: -2

Masukkan Hasil: 2
Matrix A :  
 [[ 1.  -1.   4. ]
 [ 0.   5.  -2. ]
 [ 0.   0.  -7.2]]
Nilai X  3 = 2.0000000000000004
Nilai X  2 = -2.0
Nilai X  1 = 1.9999999999999982

```



**Eliminasi Gauss Jacobi**

Metode iterasi jacobi merupakan salah satu bidang analisis numerik yang digunakan untuk menyelesaikan permasalahan persamaan linier dan sering dijumpai dalam berbagai disiplin ilmi. Metode iterasi jacobi merupakan salah satu metode tak langsung, yaitu bermula dari suatu hampiran penyelesaian awal dan kemudian berusaha memperbaiki hampiran dalam tak terhingga namun langkah konvergen. Metode iterasi jacobi ini digunakan untuk menyelesaikan linier berukuran besar dan proporsi koefisien nolnya besar.

Jika ingin mengubah dalam sistem persamaan linier, maka dapat ditulis sebagai berikut:
$$
A_{x}=b
$$
Kemudian diketahui bahwa A= D + (L + U), dimana D merupakan matriks diagonal, L merupakan matrisk segitiga bawah, dan U merupakan matriks segitiga atas. Lalu persamaan tersebut diubah menjadi sebagai berikut:
$$
D_{x}+ (L+U)x=b
$$

$$
x=D^-1[b-(L+U)x]
$$

Jika ditulis dalam aturan iteratif, maka metode itersai jacobi dapat ditulis sebagai berikut:
$$
X^{(k)}=D^-1(b-(L+U)X^{(k-1)}
$$
Dimana k merupakan banyaknya iterasi. Jika x_k menyatakan hampiran ke - k penyelesaian SPL, maka x_0 adalah hampiran awal.
$$
x_{i}^{(k)}=\frac{1}{a_{ii}}(\sum x^{n}_{j\ne i}),i = 1,2,...n;k=1,2,3,...,
$$


Suatu matriks A berukuran n x n dikatakan dominan secara diagonal jika:


$$
|a_{ii}|>|a_{i,1}|+...+|a_{i,i-1}|+|a_{i,i+1}|+...+|a_{in}|
$$


**Source Code**

```phyton
rom pprint import pprint
from numpy import array, zeros, diag, diagflat, dot
import numpy as np

def jacobi(A,b,N=25,x=None):
        #Membuat iniial guess                                                                                                                                                         
    if x is None:
        x = zeros(len(A[0]))

    #Membuat vektor dari elemen matrix A                                                                                                                                                                                                                                                                                                                 
    D = diag(A)
    R = A - diagflat(D)

    #Iterasi                                                                                                                                                                        
    for i in range(N):
        x = (b - dot(R,x)) / D
    return x

Mat1 = []
Mat2 = []

n = int(input("Masukkan ukuran Matrix: "))
for i in range(n):
    baris=[]
    for i in range(n):
        a=int(input("Masukkan Nilai: "))
        baris.append(a)
    Mat1.append(baris)
for i in range(n):
    h = int(input("Masukkan Hasil: "))
    Mat2.append(h)

A = array(Mat1,float)
b = array(Mat2,float)
x=len(Mat1)
guess = np.zeros(x,float)

sol = jacobi(A,b,N=25,x=guess)

print("A:")
pprint(A)

print("b:")
pprint(b)

print("x:")
pprint(sol)
A = array(Ma
```

**Output:**

```phyton
Masukkan ukuran Matrix: 3

Masukkan Nilai: 5

Masukkan Nilai: 1

Masukkan Nilai: 2

Masukkan Nilai: 5

Masukkan Nilai: 5

Masukkan Nilai: 1

Masukkan Nilai: 2

Masukkan Nilai: 1

Masukkan Nilai: 2

Masukkan Hasil: 3

Masukkan Hasil: 4

Masukkan Hasil: 2
A:
array([[5., 1., 2.],
       [5., 5., 1.],
       [2., 1., 2.]])
b:
array([3., 4., 2.])
x:
array([0.48290144, 0.57758114, 0.74168875])
```



**Eliminasi Gauss Seidel**

Metode gauss seidel digunakan untuk menyelesaikan sistem persamaan linier (SPL) berukuran besar dan proporsi koefisien nolnya besar, seperti sistem-sistem yang banyak ditemukan dalam sistem persamaan diferensial. Metode iterasi gauss seidel dikembangkan dari gagasan metode iterasi pada solusi persamaan tak linier. 

Teknik iterasi jarang digunakan untuk menyelesaikan SPL berukuran kecil karena metode-metode langsung seperti metode eliminasi gauss lebih efisien daripada metode iteratif. namun untuk SPL berukuran besar dengan presentase elemen nol pada matriks koefisien besar, teknik iterasi lebih efisien daripada metode langsung dalam hal penggunaan memori komputer maupun waktu komputasi. Dengan metode iterasi gauss seidel sesatan pembulatan dapat diperkecil karena dapat meneruskan iterasi sampai solusinya seteliti mungkin sesuai dengan batas sesatan yang diperbolehkan.

Rumus umum untuk iterasi gauss seidel:
$$
x_{i} = \frac{1}{a_{ii}}(b_{i}-\sum_{j=1}^{i-1}a_{ij}x_{j}^{(k)}-\sum_{j=i+1}^{n}a_{ij}x_{j}^{(k-1)}), i = 1,2,...,n;k=1,2,3,...
$$



**Source Code**

```phyton
def seidel(a, x ,b): 
    #Mencari Panjang Matrix  
    n = len(a)               
    for j in range(0, n):        
        d = b[j]                 
        #Menghitung xi, yi, zi 
        for i in range(0, n):    
            if(j != i): 
                d-=a[j][i] * x[i]        
        x[j] = d / a[j][j] #Solusi   
    return x     

m=int(input("Masukkan Panjang Matrix: "))
a=[]
b=[]
for k in range(m):
    mat1=[]
    for i in range(m):
        l=float(input("Masukkan a"+str(k+1)+","+str(i+1)+": "))
        mat1.append(l)
    h=float(input("Masukkan Hasil: "))
    b.append(h)
    a.append(mat1)

n = 3                           
x = [0, 0, 0]                        
print(x) 

for i in range(0, 100):          
    x = seidel(a, x, b)
    print(x)                       
```

**Output:**

```phyton
Masukkan Panjang Matrix: 3

Masukkan a1,1: 4

Masukkan a1,2: -1

Masukkan a1,3: 1

Masukkan Hasil: 7

Masukkan a2,1: 4

Masukkan a2,2: -8

Masukkan a2,3: 1

Masukkan Hasil: -21

Masukkan a3,1: -2

Masukkan a3,2: 1

Masukkan a3,3: 5

Masukkan Hasil: 15
[0, 0, 0]
[1.75, 3.5, 3.0]
[1.875, 3.9375, 2.9625]
[1.99375, 3.9921875, 2.9990625]
[1.99828125, 3.9990234375, 2.9995078125]
[1.99987890625, 3.9998779296875, 2.9999759765625003]
[1.99997548828125, 3.9999847412109375, 2.999993247070312]
[1.9999978735351562, 3.9999980926513667, 2.999999530883789]
[1.9999996404418945, 3.9999997615814205, 2.9999999038604734]
[1.9999999644302369, 3.9999999701976776, 2.9999999917325595]
[1.9999999946162794, 3.9999999962747097, 2.99999999859157]
[1.9999999994207849, 3.9999999995343387, 2.9999999998614464]
[1.9999999999182232, 3.999999999941793, 2.999999999978931]
[1.9999999999907154, 3.999999999992724, 2.9999999999977414]
[1.9999999999987457, 3.9999999999990905, 2.9999999999996803]
[1.9999999999998526, 3.9999999999998863, 2.9999999999999636]
[1.9999999999999807, 3.999999999999986, 2.999999999999995]
[1.9999999999999978, 3.9999999999999987, 2.9999999999999996]
[1.9999999999999996, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
```

