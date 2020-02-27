## **1. Mean(Rata-rata)**
Pengertian mean adalah nilai rata-rata dari beberapa buah data. Nilai mean dapat ditentukan dengan cara membagi jumlah data dengan banyaknya data.
Rumus untuk mencari mean seperti berikut:
$$
\overline{x}=\frac{\sum_{i=1}^{N} x_{i}}{N}=\frac{x_{1}+x_{2}+\cdots+x_{N}}{N}
$$

## **2. Median**

pengertian median adalah suatu cara untuk menentukan letak tengah sebuah data setelah data disusun menurut urutan nilainya.
Rumus untuk mencari median seperti berikut:

$$
M e=x_{i j}+\left(\frac{\frac{n}{2}-f_{k i j}}{f_{i}}\right) p
$$

## **3. Modus**

Pengertian modus adalah nilai yang sering muncul. Untuk ingin melihat suatu hasil akhir dari modus maka harus menentukan kelas pada tabel dengan memilih frekuensi yang paling banyak.
Rumus untuk mencari modus seperti berikut:

$$
\text { mean }-\text { mode } \approx 3 \times(\text { mean }-\text { median })
$$

## **4. Standard deviasi**

Pengertian standard deviasi adalah nilai statistik yang digunakan untuk menentukan bagaimana sebaran data dalam sampel, dan seberapa dekat titik data individu ke mean atau rata-rata nilai sampel.

Rumus untuk mencari standard deviasi sebagai berikut:

$$
\sigma ^ { 2 } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( x _ { i } - \overline { x } ) ^ { 2 } = ( \frac { 1 } { N } \sum _ { i = 1 } ^ { N } x _ { i } ^ { 2 } ) - \overline { x } ^ { 2 }
$$	

## **5. Varian **

Pengertian varian adalah ukuran seberapa jauh sebuah kumpulan bilangan tersebar, varian juga merupakan salah satu pendeskripsi dari sebuah distribusi probabilitas.
Rumus untuk mencari devian sebagai berikut:

$$
\sigma = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( x _ { i } - \overline { x } ) ^ { 2 } = ( \frac { 1 } { N } \sum _ { i = 1 } ^ { N } x _ { i } ^ { 2 } ) - \overline { x } ^ { 2 }
$$

## **6. Skewness (Kemiringan)**

Pngertian skewness adalah derajat ketidaksimetrisan atau distribusi.

Rumus untuk mencari skewness sebagai berikut:

$$
s k=\frac{\overline{X}-M o}{s}
$$

## **7.Kuartil**
Pengertian kuartil adalah nilai-nilai yang membagi data yang telah diurutkan kedalam empat bagian yang nilainya sama besar, Kuartil terbagi menjadi 3 macam antara lain:

a) Kuartil bawah (k1)

b) kuartil tengah (k2)

c)) Kuartil atas (k3)

Rumus untuk memcri kuartil 1,2, dan 3 sebagai berikut:

$$
IQR=Q3−Q1
$$
```python
import pandas as pd
from scipy import stats
import numpy as np
import seaborn as sns
import matplotlib as plt
data = pd.read_csv("ANDIAJADOANG.csv",delimiter=";")
cm = sns.light_palette("gold", as_cmap=True)
data.style.background_gradient(cmap=cm)

colum = data.columns.tolist()
for x in colum :
    ds = [x for x in data[x]]
    desc = data[x].describe()
    array = [x for x in desc]
    print("Detail kolom",x)
    print("rata-rata: ",array[1])
    print("Median: ",np.median(np.array(ds)))
    print("Modus: ",stats.mode(ds))
    print("Standard deviasi: ",np.std(ds))
    print("varian: ",stats.variation(ds))
    print("Skewness: ",stats.skew(ds))
    print("Quartil 1: ",array[4])
    print("Quartil 2: ",array[5])
    print("Quartil 3: ",array[6])
    sns.distplot(data[x])
    
```



​    
