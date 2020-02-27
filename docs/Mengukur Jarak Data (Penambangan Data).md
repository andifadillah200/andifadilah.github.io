## **1. Mengukur Jarak Tipe Numerik**
Ada beberapa ukuran similaritas data ukuran jarak, diantaranya:
### a) Minkowski Distance
Kelompok Minkowski diantaranya adalah Euclidean distance dan Manhattan distance, Minkowski distance dinyatakan dengan:
$$
\begin{align}
d _ { \operatorname { min } } = ( \sum _ { i = 1 } ^ { n } | x _ { i } - y _ { i } | ^ { m }  ) ^ { \frac { 1 } { m } } , m \geq 1
\end{align}
$$

### b) Manhattan Distance
Manhattan distance ialah kasus khusus dimana jarak dari minkoswski distance pada m= 1. Manhattan distance sensitif terhadap outlier. Jika ukuran ini digunakan dalam algoritma cleustering maka bentuk cleuster adalah hyper-rectangular. Ukuran ini dinyatakan dengan:
$$
d _ { \operatorname { man } } = \sum _ { i = 1 } ^ { n } \left| x _ { i } - y _ { i } \right|
$$

### c) Euclidean Distance
Euclidean distance ialah metode pengukuran yang paling sering digunakan, euclidean distance menghitung akar dari kuadrat perbedaan dua buah atau lebih vektor. Metode ini dapat digunakan untuk mendeteksi tingkat ketidaksamaan citra dengan cara mengisi nilai vektor p dan q dengan nilai fitur citra yang akan dideteksi tingkat ketidaksamaannya. Euclidean distance memiliki kelemahan yaitu jika dua vektor data tidak memiliki nilai atribut yang sama, kemungkinan memiliki jarak yang lebih kecil daripada pasangan vektro data lainnya yang mengandung nilai atribut yang sama.

### d) Average Distance
Dikarenakan kekurangan dari jarak euclidian distance diatas, maka rata-rata jarak adalah versi modifikasi dari jarak euclidian distance untuk memperbaiki hasil. Rata-rata jarak didefinisikan dengan:
$$
d _ { a v e } =  \left ( \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } \right) ^ { \frac { 1 } { 2 } }
$$

### e) Weighted Euclidean Distance
Jika berdasarkan tingkat penting dari masing-masing atribut ditentukan, maka weihted euclidean distance adalah modifikasi lain dari jarak euclidean distance yang dapat digunakan. Ukuran ini didefinisikan dengan:
$$
d _ { w e } = \left ( \sum _ { i = 1 } ^ { n } w _ { i } ( x _ { i } - y _ { i } \right) ^ { 2 } ) ^ { \frac { 1 } { 2 } }
$$

### f) Chord Distance
Chord distance adalah salah satu ukuran modifikasi euclidean distance untuk mengatasi kekurangan dari euclidean distance. Jarak ini dapat juga dihitung dari data yang tidak dinormalisasi, Chord distance didefinisikan dengan:
$$
d _ { w e } = \left ( \sum _ { i = 1 } ^ { n } w _ { i } ( x _ { i } - y _ { i } \right) ^ { 2 } ) ^ { \frac { 1 } { 2 } }
$$

### g) Mahalanobis Distance
Jarak mahalanobis yang teratur dapat digunakan untuk mengekstaksi hyperellipsoidal clusters. Jarak mahanalobis dapat mengurangi distorsi yang disebabkan oleh korelasi linier antar fitur dengan menerapkan transformasi pemutihan ke data atau dengan menggunakan kuadrat jarak mahalanobis. Mahalanobis distance didefinisikan dengan:
$$
d _ { m a h } = \sqrt { ( x - y ) S ^ { - 1 } ( x - y ) ^ { T } }
$$

### h) Cosine Measure
Ukuran cosine similarty lebih banyak digunakan dalam similaritas dokumen dan didefinisikan dengan:
$$
Cosine(x,y)=\frac { \sum _ { i = 1 } ^ { n } x _ { i } y _ { i } } { \| x \| _ { 2 } \| y \| _ { 2 } }
$$

### i) Pearson Correlation
Pearson correlation banyak digunakan pada data expresi gen. ukuran ini menghitung antara dua bentuk pola expresi gen. pearson corralatin didefinisikan dengan:
$$
Pearson ( x , y ) = \frac { \sum _ { i = 1 } ^ { n } ( x _ { i } - \mu _ { x } ) ( y _ { i } - \mu _ { y } ) } { \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 }
} \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } } }
$$

## **2.Mengukur Jarak Atribut Binary**
Similaritas dan desimilirity untuk objek yang dijelaskan oleh atribut biner simetris atau asimetris. Aatribut biner hanya memiliki dua status: 0 dan 1 Contoh atribut perokok menggambarkan seorang pasien, misalnya, 1 menunju kkan bahwa pasien merokok, sedangkan 0 menunjukkan pasien tidak merokok. Memperlakukan atribut biner sebagai atribut numerik tidak diperkennkan. Oleh karena itu,metode khusus untuk data biner diperlukan untuk membedakan komputasi.

### Dissimilarity dan Similarity

Rumus dissimilarity antara ii dan jj dan dinyatankan sebagai atribut biner simetris adalah:
$$
\begin{align} d(i,j) = \frac {r+s}{q+r+s+t} \end{align}
$$

Rumusmedunissimilarity antara ii d n jj dan dinyatankan sebagai atribut binimetris adalah:
$$
\begin{align} d(i,j) = \frac {r+s}{q+r+s} \end{align}
$$
Persamaan similarity **Jaccard coefficient** rumusnya adalah:
$$
\begin{align} sim(i,j) = \frac {q}{q+r+s} = 1-d(i,j) \end{align}
$$
## **3.Mengukur Jarak Menggunakan Catergorical**

### 1. Overlay Metric
Untuk semua atribut bertipe nominal, ukuran jarak yang paling sederhana adalah Overlay Metric (OM) dinyatakan dengan
$$
\begin{align} d(x,y) = \sum_{i=1}^n\delta(a_i(x),a_i(y)) \end{align}
$$
Dimana nn adalah banyaknya atribut, ai(x)ai(x) dan ai(y)ai(y) adalah nilai atribut ke ii yaitu AiAi dari masing-masing objek xx dan yy, δ(ai(x))(ai(y))δ(ai(x))(ai(y)) adalah 0 jika ai(x)ai(x) = ai(y)ai(y) dan 1 jika sebaliknya.

### 2. Value Difference Metri
VDM dikenalkan oleh Standfill and Waltz, versi sederhana dari VDM tanpa skema pembobotan didefinsisikan dengan:
$$
\begin{align} d(x,y) = \sum_{i=1}^n\sum_{c=1}^C|P(c|a_i(x)) - P(c|a_i(y)) \end{align}
$$
Dimana CC adalah banyaknya kelas, P(c|ai(x))P(c|ai(x)) adalah probabilitas bersyarat dimana kelas xx adalah cc dari atribut AiAi, yang memilki nilai ai(x)ai(x), P(c|ai(y))P(c|ai(y)) adalah probabilitas bersyarat dimana kelas y adalah c dengan atribut AiAi memiliki nilai ai(y). 

### 3. Minimum Risk Metric
Ukuran ini dipresentasikan oleh Blanzieri and Ricci, berbeda dari SFM yaitu meminimumkan selisih antara kesalahan berhingga dan kesalahan asymtotic. MRM meminimumkan risk of misclassification yang didefinisikan dengan:
$$
\begin{align} d(x,y) = \sum_{c=1}^C|P(c|x) (1 - P(c|y)) \end{align}
$$

## **4. Mengukur Jarak Tipe Ordinal**
Perlakuan untuk atribut ordinal adalah cukup sama dengan atribut numerik ketika menghitung disimilarity antara objek. Misalkan ff adalah atribut-atribut dari atribut ordinak dan nn objek. Menghitung disimilarity terhadap ff fitur sebagai berikut:
- Nilai ff untuk objek ke-ii adalah xifxif, dan ff memiliki MfMf status urutan, mewakili peringkat 1,...,Mf1,...,Mf ganti setiap XifXif dengan peringkatnya rif∈1...MMfrif∈1...MMf

- Karena setiap atribut ordinal dapat memiliki jumlah state yang berbeda, diperlukan untuk memetakan rentang setiap atribut ke [0,0, 1.0] sehingga setiap atribut memiliki bobot yang sama. Perl melakukan normalisasi data dengan mengganti peringkat rifrif dengan
$$
\begin{align} z_{if} = \frac{r_{if} - 1}{M_f - 1} \end{align}
$$
- Dissimilarity kemudian dihitung dengan menggunakan ukuran jarak seperti atribut numerik dengan data yang baru setelah ditransformasi zif

## **5. Mengukur Jarak Tipe Campuran**
$$
\begin{align} d(i,j) = \frac{\sum_{f=1}^p\delta_{ij}^{(f)} d_{ij}^{(f)}}{\sum_{f=1}^pd_{ij}^{(f)}} \end{align}
$$
```python
import pandas as pd
from scipy import stats
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data = pd.read_csv("Abalone.csv",delimiter=";")
k=data.iloc[0:18]

def jarak(v1,v2):
    return ((chordDist(v1,v2,numerical)+ordDist(v1,v2,ordinal)+categoricalDist(v1,v2,categorical)+binaryDist(v1,v2,binary))/4)

from IPython.display import HTML, display
import tabulate
table=[
    ["Data"]+["Jarak"]+["Numeric"]+["Ordinal"]+["Categorical"]+["Binary"],
    ["v1-v2"]+[0]+["{:.2f}".format(chordDist(0,1,numerical))]+["{:.2f}".format(ordDist(0,1,ordinal))]+[categoricalDist(0,1,categorical)]+[binaryDist(0,1,binary)],
    ["v1-v3"]+[0]+["{:.2f}".format(chordDist(0,2,numerical))]+["{:.2f}".format(ordDist(0,2,ordinal))]+[categoricalDist(0,2,categorical)]+[binaryDist(0,1,binary)],
    ["v2-v3"]+[0]+["{:.2f}".format(chordDist(1,2,numerical))]+["{:.2f}".format(ordDist(1,2,ordinal))]+[categoricalDist(1,2,categorical)]+[binaryDist(0,1,binary)],
    ["v3-v4"]+[0]+["{:.2f}".format(chordDist(2,3,numerical))]+["{:.2f}".format(ordDist(2,3,ordinal))]+[categoricalDist(2,3,categorical)]+[binaryDist(0,1,binary)],
    ["v4-v5"]+[0]+["{:.2f}".format(chordDist(3,4,numerical))]+["{:.2f}".format(ordDist(3,4,ordinal))]+[categoricalDist(3,4,categorical)]+[binaryDist(0,1,binary)],
    ["v5-v6"]+[0]+["{:.2f}".format(chordDist(4,5,numerical))]+["{:.2f}".format(ordDist(4,5,ordinal))]+[categoricalDist(4,5,categorical)]+[binaryDist(0,1,binary)],
    ]

display(HTML(tabulate.tabulate(table, tablefmt='html')))
```
