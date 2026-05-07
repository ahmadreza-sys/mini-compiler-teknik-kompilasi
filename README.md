# Mini Compiler - Teknik Kompilasi

## Nama
Ahmad Reza

## Nim
231011403385

## Mata Kuliah
Teknik Kompilasi

## Deskripsi
Program mini compiler sederhana menggunakan:
- Lexer
- Parser
- AST
- TAC

Program mendukung operator:
- +
- -
- *
- /
- ^

## Contoh Input
a ^ 2 + b * c

## Contoh Output
t1 = a ^ 2
t2 = b * c
t3 = t1 + t2

# Jawaban Pertanyaan Refleksi

## 1. Mengapa fungsi power() harus dipanggil di dalam term(), bukan sebaliknya?

Karena operator pangkat (^) memiliki prioritas lebih tinggi dibandingkan operator perkalian (*) dan pembagian (/).

Dengan memanggil power() di dalam term(), maka operasi pangkat akan diproses lebih dahulu sebelum operasi perkalian atau pembagian.

Contoh:
a ^ 2 * b

Akan diproses menjadi:
(a ^ 2) * b

Hal ini sesuai dengan aturan Operator Precedence dalam matematika.


## 2. Apa yang terjadi jika variabel z digunakan tetapi tidak ada di symbol_table?

Pada fase Analisis Semantik, compiler akan menghasilkan error:

Semantic Error: Undefined variable 'z'

Karena variabel tersebut belum didefinisikan di dalam symbol_table.

Tujuan semantic analysis adalah memastikan semua variabel valid sebelum program dijalankan.


## 3. Mengapa instruksi a ^ 2 harus muncul sebelum + pada TAC?

Karena operator pangkat memiliki prioritas lebih tinggi dibandingkan operator penjumlahan.

Compiler harus menghitung operasi pangkat terlebih dahulu sebelum melakukan operasi penjumlahan.

Contoh TAC:

t1 = a ^ 2
t2 = b * c
t3 = t1 + t2

Urutan ini memastikan hasil perhitungan sesuai aturan matematika.
