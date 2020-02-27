# **Regresi Linier**
<table>
<thead>
  <tr>
    <th>x1</th>
    <th>x2</th>
    <th>y</th>
  </tr>
 </thead>
 <tbody>
  <tr>
    <td>2</td>
    <td>3</td>
    <td>5</td>
  </tr>
  <tr>
    <td>3</td>
    <td>2</td>
    <td>5</td>
  </tr>
  <tr>
    <td>6</td>
    <td>2</td>
    <td>8</td>
  </tr>
  <tr>
    <td>4</td>
    <td>1</td>
    <td>6</td>
  </tr>
  <tr>
    <td>8</td>
    <td>2</td>
    <td>10</td>
  </tr>
  <tr>
    <td>7</td>
    <td>4</td>
    <td>10</td>
  </tr>
 </tbody>
</table>

<table>
<thead>
  <tr>
    <th>x1</th>
    <th>x2</th>
    <th>y</th>
    <th>x1y</th>
    <th>x2y</th>
    <th>x1x2</th>
    <th>x1^2</th>
    <th>x2^2</th>
    <th>y^2</th>
  </tr>
  </thead>
  <tbody>
  <tr>
    <td>2</td>
    <td>3</td>
    <td>5</td>
    <td>10</td>
    <td>15</td>
    <td>6</td>
    <td>4</td>
    <td>9</td>
    <td>25</td>
  </tr>
  <tr>
    <td>3</td>
    <td>2</td>
    <td>5</td>
    <td>15</td>
    <td>10</td>
    <td>6</td>
    <td>9</td>
    <td>4</td>
    <td>25</td>
  </tr>
  <tr>
    <td>6</td>
    <td>2</td>
    <td>8</td>
    <td>48</td>
    <td>16</td>
    <td>12</td>
    <td>36</td>
    <td>4</td>
    <td>64</td>
  </tr>
  <tr>
    <td>4</td>
    <td>1</td>
    <td>6</td>
    <td>24</td>
    <td>6</td>
    <td>4</td>
    <td>16</td>
    <td>1</td>
    <td>36</td>
  </tr>
  <tr>
    <td>8</td>
    <td>2</td>
    <td>10</td>
    <td>80</td>
    <td>20</td>
    <td>16</td>
    <td>64</td>
    <td>4</td>
    <td>100</td>
  </tr>
  <tr>
    <td>7</td>
    <td>4</td>
    <td>10</td>
    <td>70</td>
    <td>40</td>
    <td>28</td>
    <td>49</td>
    <td>16</td>
    <td>100</td>
  </tr>
  <tr>
    <td>30</td>
    <td>14</td>
    <td>44</td>
    <td>247</td>
    <td>107</td>
    <td>72</td>
    <td>178</td>
    <td>38</td>
    <td>350</td>
  </tr>
  </tbody>
</table>
$$
A= n . \sum x_1y - (\sum  x_1)(\sum y)= 6*247-30*44= 1482-1320= 162 
$$

$$
B= n . \sum x_2^2 - (\sum  x_2)^2-(\sum X_2)^2= 6*38-196= 228-196= 32
$$

$$
C= n . \sum X_1 X_2- (\sum X_1)(\sum X_2)= 6*72-30*14= 432-420= 12
$$

$$
D= n . \sum X_2Y- (\sum X_2)(\sum Y)= 6*107- 14*44= 642-616= 26
$$

$$
E= n. \sum X_1^2-(\sum X_1)^2 = 6*178-900=1068-900= 168
$$

$$
F= EB- C = 168*32-12=5376-12 =5354
$$

$$
b1= \frac{AB - CD}{F} = \frac{(162)(32) - (12)(26)}{5354}= \frac{5184- 312}{5354}= \frac{4872}{5354}= 0,909
$$

$$
b2= \frac{DE - AC}{F} = \frac{(32)(168) - (162)(12)}{5354}= \frac{5376 - 1644}{5354}= \frac{3432}{5354}= 0,641
$$

$$
a= \frac{\sum y- b_1\sum x_1- b_2\sum x_2}{n} = \frac{44-(0,909) (30)- (0,641)(14)}{6}= \frac{7,756=}{6}= 1,292
$$
Hasil Akhir
$$
{y}'= 1,292 + 0,909x_1 + 0,641 x_2
$$

Pengecekan
$$
x1	=	2
$$
$$
x2	=	8
$$
$$
y = a + b1x1 + b2x2
$$

```python
import numpy as np
from sklearn.linear_model import LinearRegression
X = np.array([[2, 3], [3, 2], [6, 2], [4, 1], [8, 2], [7, 4]])
y = np.array([5, 5, 8, 6, 10, 10])
X 
```
output:
```python
array([[2, 3],
       [3, 2],
       [6, 2],
       [4, 1],
       [8, 2],
       [7, 4]])
```
```python
reg = LinearRegression().fit(X, y)
reg.score(X, y)
```
output
```python
0.9932870888341911
```
```python
a = reg.intercept_
a
```
output
```python
1.5963302752293584
```
```python
b2 = reg.coef_[1]
b1 = reg.coef_[0]
x1 = 6
x2 = 2
b2
```
output
```python
0.46330275229357804
```
```python
y = b1*x1 + b2*x2 + a
y
```
output
```python
16.0
```
```python
reg.predict(np.array([[2, 8]]))
```
output
```python
array([7.16513761])
```
