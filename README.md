# Pertemuan 11 - Dictionary/Map
- Nama: Tantri Widya Solehati
- NIM: 2225250114
- Kelas: 3F
## Tujuan
Memodelkan data pendidikan menggunakan dictionary dan pasangan key-value.
## Struktur Data
Pada struktur data_mahasiswa, yang menjadi key utama adalah NIM mahasiswa, sedangkan value-nya adalah dictionary (kamus) berisi data mahasiswa.
## Cara Menjalankan
python3 praktik/data_mahasiswa.py
## Test Case
| No | Kasus | Input/Aksi | Hasil yang Diharapkan | Hasil Aktual | Status | 
|----|-------|------------|-----------------------|--------------|--------|
| 1 | Pencarian tersedia | A003 | Data Citra ditampilkan | Data Citra ditampilkan | Sesuai |
| 2 | Pencarian tidak tersedia | A999 | Pesan 'Data tidak ditemukan' | Data tidak ditemukan | Sesuai | 
| 3 | Pembaruan nilai | A002 menjadi 82 | Nilai A002 berubah menjadi 82 | Nilai A002 berubah menjadi 82 | Sesuai | 
| 4 | Penambahan data | A006 | Key A006 tersedia setelah ditambahkan| Key A006 tersedia setelah ditambahkan| Sesuai | 
| 5 | Rekap | items() | Semua NIM dan data tampil | Semua NIM dan data tampil | Sesuai |
## Refleksi
- Satu kesalahan akses key yang mungkin terjadi pada program ini adalah saat mencoba mengakses key yang tidak ada di dalam dictionary.
    Contoh salah:
```Python
print(data_mahasiswa["A007"])
```
Karena key "A007" tidak ada di data_mahasiswa, Python akan menghasilkan error:
```Plain Text
KeyError: 'A007'
Cara memperbaikinya
1. Gunakan get()
```Python
mahasiswa = data_mahasiswa.get("A007")
if mahasiswa is not None:
print(mahasiswa)
else:
print("Data tidak ditemukan")
```
Metode get() akan mengembalikan None jika key tidak ditemukan, sehingga program tidak error.

2. Cek keberadaan key terlebih dahulu
```Python
if "A007" in data_mahasiswa:
print(data_mahasiswa["A007"])
else:
print("Data tidak ditemukan")
 ```
Contoh kesalahan lain pada dictionary bersarang
Misalnya:
```Python
print(data_mahasiswa["A003"]["umur"])
```
Error:
KeyError: 'umur'

Karena data mahasiswa hanya memiliki key:
```Python
"nama"
"kelas"
"nilai"
```
dan tidak memiliki key "umur".
Perbaikannya:
```Python
print(data_mahasiswa["A003"].get("umur", "Data umur tidak tersedia"))
Output:
Plain Text
Data umur tidak tersedia
Kesimpulan: Kesalahan akses key terjadi ketika program mencoba mengambil data dengan key yang tidak ada dalam dictionary. Cara aman untuk memperbaikinya adalah menggunakan .get() atau memeriksa keberadaan key dengan in sebelum mengaksesnya.