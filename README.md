# PRATIKUM 3

# Tugas Praktikum

1. Lakukan penambahan data pada table mahasiswa dengan mengisi kd_ds yang
belum ada pada data dosen.
2. Hapus satu record data pada table dosen yang telah dirujuk pada tabel
mahasiswa.
3. Ubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRICT
4. Lakukan perubahan data pada table dosen (kd_ds)
5. Lakukan penghapusan data pada table dosen
6. Ubah mode menjadi ON UPDATE CASCADE ON DELETE SET NULL
7. Lakukan penghapusan data pada table dosen

# Penjelasan

1.Lakukan penambahan data pada table mahasiswa dengan mengisi kd_ds yang
belum ada pada data dosen.

`Jawab :`
Pada tabel mahasiswa dan dosen saya menginput data seperti diabwah ini:
# Untuk mahasiswa:

![gambar4](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/57f11a1e-5a33-4a63-8454-9c7e26256160)

# Untuk dosen:

![gambar3](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/6b662de0-066e-4477-8da4-58cc38446aa6)

Untuk perintahnya bisa menggunakan:
` INSERT INTO mahasiswa
VALUES (“312210378”, “Mikael Rivaldo”, “L”, “24 Mei 2004”, “Rusa”, “Bekasi”, 
“1999”, “895014439”, “M003”); `

2.Hapus satu record data pada table dosen yang telah dirujuk pada tabel
mahasiswa.
`Jawab :`

![gambar12png](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/d9dee21c-85d3-43e1-a8f8-f5be07769eab)

`#NOTE` : Hal ini akan terjadi eror(dosen) karena data yang kita hapus terhubung ke mahasiswa

Contoh EROR seperti di bawah ini :

![gambarr9](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/60b7ec41-b3a7-4048-8e9d-40f3133b022b)

3. Ubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRICT

`Jawab :`

Untuk Perintahnya bisa menggunakan  :

`ALTER TABLE mahasiswa
DROP FOREIGN KEY mahasiswa_ibfk_1;
ALTER TABLE mahasiswa
DROP KEY kd_ds;`

bisa di lihat pada bagian kd_ds bahwa kuncinya sudah hilang
![gambar2 edit](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/f4697387-1027-4b3c-92cb-087c149d3b91)

Untuk perintahnya ON UPDATE CASCADE ON DELETE RESTRICT bisa menggunakan seperti dibawah ini:

`ALTER TABLE mahasiswa
ADD FOREIGN KEY (kd_dosen)
REFERENCES dosen(kd_dosen)
ON UPDATE CASCADE ON DELETE RESTRICT`

4.Lakukan perubahan data pada table dosen (kd_ds)

`Jawab :`

Untuk melalukan delete pada table dosen bisa menggunakan perintah ini:

`UPDATE dosen
SET kd_ds = “M002”,WHERE kd_ds = “M005”;`

# Untuk mahasiswa
`Sebelum`
![gambar4](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/d32acbd2-136e-4855-98de-cdf19baaa544)

`Sesudah`
![gambar8](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/160de98b-8dbe-4281-a30f-200dce7d7a67)



# Untuk dosen

`Sebelum`
![gambar3](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/b3d9ffe5-ddd2-4010-af00-5c0a586873e5)

`Sesudah`
![gambar7](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/3f678ee4-89c2-4b8c-97b3-be449f69718d)

`Note` : Bisa dilihat di gambar di atas pada kd_ds yang sebelumnya "M002" menjadi "M005" dan selanjutnya pada tabel mahasiswa juga ikut berubah, karena perintah ON 
UPDATE CASCADE ON DELETE RESTRICT yang kita tambahkan sebelum nya.


5. Lakukan penghapusan data pada table dosen

`Jawab`:

![gambarr9](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/7197074d-71f2-4f9e-b721-1197f7626524)


`Note` : : Ini karena ON DELETE RESTRICT berarti bahwa jika terdapat baris pada 
tabel induk (parent table) yang akan dihapus dan masih terdapat referensi dari kolom 
anak (child key) ke baris tersebut, maka penghapusan baris pada tabel induk tersebut 
tidak akan diizinkan atau di-restrict.

6.Ubah mode menjadi ON UPDATE CASCADE ON DELETE SET NULL

`Jawab`:

# Untuk cara ini sama seperti no 3 yaitu,yaitu menghapus FOREIGN KEY & ON
UPDATE CASCADE ON DELETE RESTRICT terlebih dahulu dan menambahkan 
ON UPDATE CASCADE ON DELETE SET NULL.

# Untuk perintah bisa menggunakan cara ini:

ALTER TABLE mahasiswa
ADD FOREIGN KEY (kd_ds)
REFERENCES dosen(kd_ds)
ON UPDATE CASCADE ON DELETE SET NULL

Untuk gambar seperti dibawah ini:

![gambar2](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/6e586475-1190-4e41-9440-e116b187e3bb)

7. Lakukan penghapusan data pada table dosen

`Jawab`:

`Sebelum`

![gambar12png](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/f2f547d2-3d38-4a17-b32e-b4d60fa9d23d)


`Sesudah`

![gambar10](https://github.com/MikaelRivaldo/pratikum3/assets/115770247/a888f2a2-4857-45ae-804c-6232c0611772)
















