# Tugas Praktikum 
Buat program sederhana yang akan menampilkan daftar nilai
mahasiswa, dengan ketentuan
• Program dibuat dengan menggunakan Dictionary
• Tampilkan menu pilihan: (Tambah Data, Ubah Data, Hapus Data,
Tampilkan Data, Cari Data)
• Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas: 30%,
uts: 35%, uas: 35%)
• Buat flowchart dan penjelasan programnya pada README.md. • Commit dan push repository ke github.

## kode program 
```python
# Program Manajemen Nilai Mahasiswa
mahasiswa = {}

def tambah_data():
    print("\nTambah Data Mahasiswa")
    nim = input("Masukkan NIM: ")
    if nim in mahasiswa:
        print("NIM sudah ada!")
    else:
        nama = input("Masukkan Nama: ")
        tugas = float(input("Masukkan Nilai Tugas: "))
        uts = float(input("Masukkan Nilai UTS: "))
        uas = float(input("Masukkan Nilai UAS: "))
        akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir}
        print("Data berhasil ditambahkan!")

def ubah_data():
    print("\nUbah Data Mahasiswa")
    nim = input("Masukkan NIM: ")
    if nim in mahasiswa:
        nama = input(f"Masukkan Nama baru [{mahasiswa[nim]['nama']}]: ") or mahasiswa[nim]['nama']
        tugas = float(input(f"Masukkan Nilai Tugas baru [{mahasiswa[nim]['tugas']}]: ") or mahasiswa[nim]['tugas'])
        uts = float(input(f"Masukkan Nilai UTS baru [{mahasiswa[nim]['uts']}]: ") or mahasiswa[nim]['uts'])
        uas = float(input(f"Masukkan Nilai UAS baru [{mahasiswa[nim]['uas']}]: ") or mahasiswa[nim]['uas'])
        akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir}
        print("Data berhasil diubah!")
    else:
        print("NIM tidak ditemukan!")

def hapus_data():
    print("\nHapus Data Mahasiswa")
    nim = input("Masukkan NIM: ")
    if nim in mahasiswa:
        del mahasiswa[nim]
        print("Data berhasil dihapus!")
    else:
        print("NIM tidak ditemukan!")

def tampilkan_data():
    print("\nDaftar Nilai Mahasiswa")
    print("===================================================================")
    print("| NIM       | Nama            | Tugas  | UTS    | UAS    | Akhir  |")
    print("===================================================================")
    for nim, data in mahasiswa.items():
        print(f"| {nim:<9} | {data['nama']:<15} | {data['tugas']:<6} | {data['uts']:<6} | {data['uas']:<6} | {data['akhir']:<6} |")
    print("===================================================================")

def cari_data():
    print("\nCari Data Mahasiswa")
    nim = input("Masukkan NIM: ")
    if nim in mahasiswa:
        data = mahasiswa[nim]
        print("\nData Mahasiswa")
        print(f"NIM       : {nim}")
        print(f"Nama      : {data['nama']}")
        print(f"Nilai Tugas : {data['tugas']}")
        print(f"Nilai UTS : {data['uts']}")
        print(f"Nilai UAS : {data['uas']}")
        print(f"Nilai Akhir: {data['akhir']}")
    else:
        print("NIM tidak ditemukan!")

def menu():
    while True:
        print("\nMenu:")
        print("1. Tambah Data")
        print("2. Ubah Data")
        print("3. Hapus Data")
        print("4. Tampilkan Data")
        print("5. Cari Data")
        print("6. Keluar")
        pilihan = input("Pilih menu: ")
        if pilihan == "1":
            tambah_data()
        elif pilihan == "2":
            ubah_data()
        elif pilihan == "3":
            hapus_data()
        elif pilihan == "4":
            tampilkan_data()
        elif pilihan == "5":
            cari_data()
        elif pilihan == "6":
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid!")

if __name__ == "__main__":
    menu()
```
## output program
```python
Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu: 1

Tambah Data Mahasiswa
Masukkan NIM: 2223334
Masukkan Nama: ruyu
Masukkan Nilai Tugas: 45
Masukkan Nilai UTS: 78
Masukkan Nilai UAS: 90
Data berhasil ditambahkan!

Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu: 2

Ubah Data Mahasiswa
Masukkan NIM: 2223334
Masukkan Nama baru [ruyu]: abi
Masukkan Nilai Tugas baru [45.0]: 0
Masukkan Nilai UTS baru [78.0]: 87
Masukkan Nilai UAS baru [90.0]: 89
Data berhasil diubah!

Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu: 3

Hapus Data Mahasiswa
Masukkan NIM: 2223334
Data berhasil dihapus!

Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu: 4

Daftar Nilai Mahasiswa
===================================================================
| NIM       | Nama            | Tugas  | UTS    | UAS    | Akhir  |
===================================================================
===================================================================

Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu: 6
Keluar dari program.
PS C:\Users\NANDA\Documents\Buat Coding\codingan 14 nov>
```
## Penjelasan Tugas
Tugas ini mengharuskan kita membuat program Python sederhana menggunakan dictionary untuk menyimpan data mahasiswa,
dengan fitur pengelolaan data seperti menambah, mengubah, menghapus, menampilkan, dan mencari data. Program juga harus
memiliki menu interaktif, menggunakan formula tertentu untuk menghitung nilai akhir, dan perlu dibuat README.md untuk dokumentasi.

1. Gunakan Dictionary
Dictionary adalah struktur data utama untuk menyimpan data mahasiswa.
Setiap NIM mahasiswa menjadi key, sementara informasi lainnya (nama, tugas, UTS, UAS, nilai akhir) menjadi value dalam bentuk dictionary.

Contoh struktur dictionary:
``` python
mahasiswa = {
    "12345": {"nama": "Andi", "tugas": 85, "uts": 90, "uas": 80, "akhir": 85.5},
    "67890": {"nama": "Budi", "tugas": 75, "uts": 85, "uas": 88, "akhir": 82.1}
}
```
2. Tampilkan Menu Pilihan
Program harus memberikan pengguna beberapa opsi, seperti:

Tambah Data
Ubah Data
Hapus Data
Tampilkan Data
Cari Data
Keluar
Menu ini dibuat menggunakan loop agar program tetap berjalan hingga pengguna memilih keluar.

3. Perhitungan Nilai Akhir
Nilai akhir dihitung berdasarkan formula:
``` python
nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
```

Penjelasan Detail Tugas
Tugas ini mengharuskan kita membuat program Python sederhana menggunakan dictionary untuk menyimpan data mahasiswa, dengan fitur pengelolaan data seperti menambah, mengubah, menghapus, menampilkan, dan mencari data. Program juga harus memiliki menu interaktif, menggunakan formula tertentu untuk menghitung nilai akhir, dan perlu dibuat README.md untuk dokumentasi.

Analisis Tugas
1. Gunakan Dictionary
Dictionary adalah struktur data utama untuk menyimpan data mahasiswa.

Setiap NIM mahasiswa menjadi key, sementara informasi lainnya (nama, tugas, UTS, UAS, nilai akhir) menjadi value dalam bentuk dictionary.

Contoh struktur dictionary:

```python

mahasiswa = {
    "12345": {"nama": "Andi", "tugas": 85, "uts": 90, "uas": 80, "akhir": 85.5},
    "67890": {"nama": "Budi", "tugas": 75, "uts": 85, "uas": 88, "akhir": 82.1}
}
```
2. Tampilkan Menu Pilihan
Program harus memberikan pengguna beberapa opsi, seperti:

Tambah Data
Ubah Data
Hapus Data
Tampilkan Data
Cari Data
Keluar
Menu ini dibuat menggunakan loop agar program tetap berjalan hingga pengguna memilih keluar.

3. Perhitungan Nilai Akhir
Nilai akhir dihitung berdasarkan formula:
```python
nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
```

4. Fitur Program
Berikut adalah penjelasan setiap fitur yang harus ada di program:

1.Tambah Data

Meminta pengguna memasukkan:
NIM (key)
Nama
Nilai tugas, UTS, dan UAS
Menghitung nilai akhir dan menambah data ke dictionary.
Kode Contoh:

```python
nim = input("Masukkan NIM: ")
nama = input("Masukkan Nama: ")
tugas = float(input("Masukkan Nilai Tugas: "))
uts = float(input("Masukkan Nilai UTS: "))
uas = float(input("Masukkan Nilai UAS: "))
akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir}
```
2.Ubah Data

Memungkinkan pengguna memperbarui data mahasiswa berdasarkan NIM.
Menampilkan data saat ini, lalu meminta pengguna memasukkan data baru.
Kode Contoh:
```python
nim = input("Masukkan NIM yang akan diubah: ")
if nim in mahasiswa:
    tugas = float(input(f"Nilai Tugas baru (lama: {mahasiswa[nim]['tugas']}): "))
    mahasiswa[nim]["tugas"] = tugas
```
3.Hapus Data

Menghapus data mahasiswa berdasarkan NIM.
Kode Contoh:
```python
nim = input("Masukkan NIM yang akan dihapus: ")
if nim in mahasiswa:
    del mahasiswa[nim]
```
4.Tampilkan Data

Menampilkan daftar semua data mahasiswa dalam format tabel.
Kode Contoh:
```python
for nim, data in mahasiswa.items():
    print(f"{nim} | {data['nama']} | {data['tugas']} | {data['uts']} | {data['uas']} | {data['akhir']}")
```
5.Cari Data

Memungkinkan pengguna mencari data mahasiswa berdasarkan NIM.
Kode Contoh:
```python
nim = input("Masukkan NIM yang dicari: ")
if nim in mahasiswa:
    print(mahasiswa[nim])
```
6.keluar
menghentikan program dengan menutup loop

### Struktur Program
Struktur program terdiri dari beberapa fungsi untuk setiap fitur:

tambah_data()
ubah_data()
hapus_data()
tampilkan_data()
cari_data()
Semua fungsi diakses melalui menu utama yang dibuat menggunakan while loop.
