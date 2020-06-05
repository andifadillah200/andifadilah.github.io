# Monte Carlo Method

**Metode Monte Carlo** adalah algoritma komputasi yang mengandalkan pengambilan sampel acak berulang untuk mendapatkan hasil numerik. Penggunaan metode ini adalah untuk mengevaluasi integral definit, terutama integral multidimensi dengan syarat dan batasan yang rumit.

Metode ini terbukti efisien dalam memecahkan persamaan diferensial integral medan radians, sehingga metode ini digunakan dalam perhitungan iluminasi global yang menghasilkan gambar-gambar fotorealistik model tiga dimensi, dimana diterapkan dalam video games, arsitektur, perancangan, film yang dihasilkan oleh komputer, efek-efek khusus dalam film, bisnis, ekonomi, dan bidang lainnya.



## Tugas Pemrograman

1. Buatlah program untuk memverifikasi secara numerik bahwa *$\pi =\int_{0}^{2}(4-x^2)^{1/2}\, dx$*. Gunakan metode monte carlo dan 2500 angka acak. 

**Listing Program**

```python
from scipy import random
import numpy as np
import matplotlib.pyplot as plt

a = 0
b = 2
N=2500


def func(x):
    return (4-x**2)**0.5


area = []
for i in range(N):
    xrand = np.zeros(N)

    for i in range(len(xrand)):
        xrand[i] = random.uniform(a,b)
        integral = 0.0

    for i in range(N):
        integral+=func(xrand[i])

    jawab = (b-a)/float(N)*integral
    area.append(jawab)

plt.title("Hasil phi")
plt.hist(area,bins = 30, ec = 'black')
plt.xlabel("Area")
plt.show()

```

**Output**

![monte carlo](..\assets\images\montecarlo.jpeg)

2.Gunakan metode monte carlo untuk memperkirakan integral
$$
\int_{-1}^{1}\int_{-1}^{1}\int_{-1}^{1}(x^2+y^2+z^2)dx\,dy\,dz
$$
**Listing Program**

```python
from scipy import random
import numpy as np

a = -1
b = 1
N=100
xrand=np.zeros(N)
yrand=np.zeros(N)
zrand=np.zeros(N)
integral=0.0
for i in range(4):
    for i in range(len(xrand)):
        xrand[i]=random.uniform(a,b)

    for i in range(len(yrand)):
        yrand[i]=random.uniform(a,b)

    for i in range(len(zrand)):
        zrand[i]=random.uniform(a,b)

    def func(x,y,z):
        return (x**2)+(y**2)+(z**2)


    for i in range(N):
        integral+=func(xrand[i],yrand[i],zrand[i])

jawab=(b-a)/float(N)*integral
print("jawab: ",jawab)

```

**Output**

```python
jawab:  7.951233160381278
```

