# Praktikum7
```
1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua  karyawan. urutkan menurun berdasarkan besaran gaji
3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di  department yang sama dengan karyawan dengan nama yang mengandung  huruf 'K'.
4. Tampilkan data karyawan yang bekerja pada departemen yang ada di  kantor pusat.
5 Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'
dan yang gajinya lebih besar dari rata-rata gaji semua karyawan
```

1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
```
SELECT 
kr.nik,
kr.nama,
kr.id_departemen
from karyawan kr
WHERE id_departemen = (SELECT id_departemen FROM karyawan WHERE nama = 'dika');
```

<img width="481" alt="gambar1" src="https://github.com/faizdzakiramadhani/Praktikum7/assets/115913915/d9532702-301b-42cc-bf24-6b84c8b166b9">


2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua  karyawan. urutkan menurun berdasarkan besaran gaji
```
SELECT 
kr.nik,
kr.nama,
kr.gaji_pokok
from karyawan kr
WHERE gaji_pokok > (SELECT avg(gaji_pokok) FROM karyawan );
```

<img width="370" alt="gambar2" src="https://github.com/faizdzakiramadhani/Praktikum7/assets/115913915/a76e1182-3063-4ae2-b813-77f09ca24d27">


3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di  department yang sama dengan karyawan dengan nama yang mengandung  huruf 'K'.
```
SELECT 
kr.nik,
kr.nama,
kr.id_departemen
from karyawan kr
WHERE id_departemen in (SELECT id_departemen FROM karyawan WHERE nama LIKE '%K%');
```

<img width="493" alt="gambar3" src="https://github.com/faizdzakiramadhani/Praktikum7/assets/115913915/2c66d5fd-2eaf-4333-88d1-8a15b50121f9">

4. Tampilkan data karyawan yang bekerja pada departemen yang ada di  kantor pusat.
```
SELECT 
d.id_perusahaan,
kr.nik,
kr.nama,
kr.id_departemen
from karyawan kr
LEFT JOIN departemen d on d.id_departemen = kr.id_departemen
WHERE id_perusahaan = 'p01';
```

<img width="381" alt="gambar4" src="https://github.com/faizdzakiramadhani/Praktikum7/assets/115913915/f543d7c2-b064-4b61-87f9-454f75a7ade5">


5 Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'
dan yang gajinya lebih besar dari rata-rata gaji semua karyawan
```
SELECT 
kr.nik,
kr.nama,
kr.id_departemen,
kr.gaji_pokok
from karyawan kr
WHERE gaji_pokok > (SELECT avg(gaji_pokok) from karyawan) AND nama LIKE '%K%';
```

<img width="479" alt="gambar5" src="https://github.com/faizdzakiramadhani/Praktikum7/assets/115913915/b432f2b1-e80f-43e8-b0ad-f2ee7069b467">
