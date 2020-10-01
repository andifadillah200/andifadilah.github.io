**TUGAS PEMROGRAMAN DESKTOP**

**Soalan dan Jawaban Latihan **

- Buat program. deklarasi 5 variabel lakukan perhitungan rata-rata 5 nilai tsb tampilkan hasilnya 

**Listing Program no 1**

```python
nilai_1= 10
nilai_2= 35
nilai_3=20
nilai_4=5
nilai_5=2
n=5
average=(nilai_1 + nilai_2 + nilai_3 + nilai_4 + nilai_5)/n
print("hasil dari nilai rata-rata adalah:", average)

```

**Output**

```python
hasil dari nilai rata-rata adalah: 14.4
```

- Buat program menghitung luas dan keliling bangun datar dengan menerima inputan dari user 


**Listing Program no 2**

```python
print("Menghitung luas dan keliling segitiga")
a= int(input("masukkan alas:"))
t= int(input("masukkan tinggi:"))
S_kanan= int(input("masukkan sisi kanan:"))
S_kiri= int(input("masukkan sisi kiri:"))
S_bawah= int(input("masukkan sisi bawah:"))

luas= 1/2*(a*t)
keliling= S_kanan + S_kiri + S_bawah

print("luas segitiga adalah:", luas)
print("keliling segitiga adalah:", keliling)

```

**Output**

```python
Menghitung luas dan keliling segitiga
masukkan alas:7
masukkan tinggi:5
masukkan sisi kanan:2
masukkan sisi kiri:2
masukkan sisi bawah:2
luas segitiga adalah: 17.5
keliling segitiga adalah: 6
```

- Buat program untuk menghitung index massa tubuh / BMI (Body mass index) hitung BMI rumus BMI ? cari di internet ya kemudan tentukan kelompok berat badan Di bawah 18,5 = Berat badan kurang 18,5 – 22,9 = Berat badan normal 23 – 29,9 = Berat badan berlebih (kecenderungan obesitas) 30 ke atas = obesitas anda termasuk yang mana ?


**Listing Program no 3**

```python
berat= float(input("masukkan berat badan (kg):"))
tinggi= float(input("masukkan tinggi badan (m):"))
rumus= berat/((tinggi/100)**2)
if rumus < 18.5:
    print("index massa tubuh:", rumus)
    print("berat badan anda kurang!")
elif rumus <= 22.9:
    print("index massa tubuh:", rumus)
    print("berat badan anda normal.")
elif rumus <= 29.9:
    print("index massa tubuh:", rumus)
    print("berat badan anda berlebih (cenderung obesitas")
else:
    print("index massa tubuh:", rumus)
    print("anda obesitas !")
```

**Output**

```python
masukkan berat badan (kg):55
masukkan tinggi badan (m):165
index massa tubuh: 20.202020202020204
berat badan anda normal.
```

- Buat program untuk menentukan nilai maksimal dan minimal dari sejumlah nilai masukan N.


**Listing Program no 4**

```python
def angkaMax(daftar):
    Max=0
    for x in daftar:
        if x >Max:
            Max=x
    return Max
def angkaMin(daftar_1):
    Min=999
    for y in daftar_1:
        if y <Min:
            Min=y
    return Min
jumlahAngka= []
angka= int(input("masukkan banyak angka yang anda inginkan:"))
for n in range(angka):
    nilai=int(input("masukkan angka:"))
    jumlahAngka.append(nilai)
print("angka Max:", angkaMax(jumlahAngka))

print("angka Min:", angkaMin(jumlahAngka))
```

**Output**

```python
masukkan banyak angka yang anda inginkan:5
masukkan angka:12
masukkan angka:14
masukkan angka:2
masukkan angka:6
masukkan angka:8
angka Max: 14
angka Min: 2
```

- Buat program untuk menentukan validasi username dan password, dimana akan di ulang maksimal 3 kali, jika benar akan muncul komentar ” anda berhasil masuk” tapi jika tidak muncul komentar ” maaf user name dan password anda salah”


**Listing Program no 5**

```python
Username= "fadilah"
password= 990801
count=0
while count < 3:
    new_Username= input("masukkan username:")
    new_password= int(input("masukkan password:"))
    if  new_password==password and new_Username==Username : 
        print("Anda berhasil masuk")
        break
    else:
        print("Maaf username dan password anda salah")
        count+=1

```

**Output**

```python
masukkan username:FADILAH
masukkan password:990801
Maaf username dan password anda salah
masukkan username:Fadilah
masukkan password:990801
Maaf username dan password anda salah
masukkan username:fadilah
masukkan password:990801
Anda berhasil masuk
```

