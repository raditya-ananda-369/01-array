# 01-array
# Tugas Struktur Data - Sistem Pengelolaan Nilai Mahasiswa

Tugas ini dibuat untuk memenuhi tugas pertemuan 1 mata kuliah Struktur Data.
Programnya sederhana — kita input 10 nilai mahasiswa, terus diolah buat cari nilai tertinggi, terendah, rata-rata, sampai grafik kelulusan.

---

## Apa yang Dibuat?

Program ini punya 7 bagian sesuai soal:

### 1. Input 10 Nilai
User diminta memasukkan 10 nilai satu per satu. Nilai-nilai itu disimpan ke dalam sebuah **list** (array).

```python
nilai = []
for i in range(10):
    n = float(input(f"Masukkan nilai mahasiswa ke-{i+1}: "))
    nilai.append(n)
```

List itu ibarat kotak panjang yang bisa menampung banyak angka. Setiap kali input, angkanya ditambahkan ke kotak tersebut pakai `.append()`.

---

### 2. Nilai Tertinggi & Terendah
Pakai fungsi bawaan Python `max()` dan `min()` untuk langsung tahu nilai paling tinggi dan paling rendah dari list.

```python
print("Nilai tertinggi:", max(nilai))
print("Nilai terendah :", min(nilai))
```

---

### 3. Rata-rata
Semua nilai dijumlahkan pakai `sum()`, lalu dibagi jumlah datanya pakai `len()`.

```python
print("Rata-rata:", sum(nilai) / len(nilai))
```

---

### 4. Jumlah Mahasiswa Lulus (>= 60)
Program mengecek satu per satu, kalau nilainya 60 ke atas → lulus, kalau kurang dari 60 → tidak lulus.

```python
for n in nilai:
    if n >= 60:
        lulus += 1
    else:
        tidak_lulus += 1
```

---

### 5. Grafik Nilai Tertinggi & Terendah
Ditampilkan pakai diagram batang. Sumbu X adalah urutan mahasiswa (1–10), sumbu Y adalah nilainya. Dari grafik ini kita bisa langsung lihat batang mana yang paling tinggi dan paling rendah.

```python
plt.bar(range(1, 11), nilai)
plt.title("Grafik Nilai Tertinggi dan Terendah")
plt.xlabel("Mahasiswa ke-")
plt.ylabel("Nilai")
plt.show()
```

---

### 6. Grafik Data Kelulusan
Juga pakai diagram batang, tapi kali ini cuma 2 batang — **Lulus** dan **Tidak Lulus**. Jadi kita bisa langsung lihat perbandingannya.

```python
plt.bar(["Lulus", "Tidak Lulus"], [lulus, tidak_lulus])
plt.title("Grafik Data Kelulusan Mahasiswa")
plt.xlabel("Status")
plt.ylabel("Jumlah Mahasiswa")
plt.show()
```

---

### 7. Analisis Kompleksitas Tiap Operasi

Ini bagian yang menjelaskan **seberapa efisien** setiap operasi di program. Diukur pakai notasi **Big-O** — intinya, kalau jumlah datanya bertambah, seberapa banyak langkah tambahan yang dibutuhkan program?

```python
print("1. Input 10 nilai   -> O(n) : loop sebanyak jumlah data")
print("2. Cari tertinggi   -> O(n) : cek semua elemen satu per satu")
print("3. Cari terendah    -> O(n) : cek semua elemen satu per satu")
print("4. Hitung rata-rata -> O(n) : jumlahkan semua elemen")
print("5. Hitung kelulusan -> O(n) : cek semua elemen satu per satu")
print("6. Grafik nilai     -> O(n) : proses semua data untuk ditampilkan")
print("7. Grafik kelulusan -> O(1) : datanya selalu 2 (lulus & tidak lulus)")
```

**Kesimpulan:**
Semua operasi utama di program ini berjalan secara **linear — O(n)**. Artinya kalau datanya 10, ya 10 langkah. Kalau 100, ya 100 langkah. Tidak ada yang O(n²) atau lebih berat, jadi program ini sudah cukup efisien untuk kasus seperti ini.

---

## Struktur File

```
01-array/
├── Soal_01.ipynb   # file utama program
└── README.md    # penjelasan ini
```
