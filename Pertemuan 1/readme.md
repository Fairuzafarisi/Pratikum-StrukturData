Implementasi Stack di Python

Program ini menunjukkan contoh sederhana bagaimana cara kerja struktur data Stack menggunakan list di Python.
Stack menggunakan prinsip LIFO (Last In, First Out) — elemen yang terakhir masuk akan menjadi elemen pertama yang keluar.


Kode Program

stack = []

# Push
stack.append('X')
stack.append('Y')
stack.append('Z')
print("Stack:", stack)

# Pop
removed = stack.pop()
print("Pop:", removed)

# Peek
top = stack[-1]
print("Peek:", top)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)

# Size
print("Size:", len(stack))


Penjelasan

1. Inisialisasi Stack

Membuat list kosong yang nantinya digunakan sebagai tumpukan data.

stack = []


2. Push (Menambahkan Data)

Menambah elemen ke bagian paling atas stack menggunakan append().

stack.append('X')
stack.append('Y')
stack.append('Z')

Setelah langkah ini, isi stack menjadi: ['X', 'Y', 'Z']


3. Pop (Menghapus Data Teratas)

Menghapus elemen paling atas menggunakan pop() tanpa indeks.

removed = stack.pop()

Elemen 'Z' adalah yang keluar dari stack.


4. Peek (Melihat Data Teratas)

Melihat elemen paling atas tanpa menghapusnya.

top = stack[-1]

Elemen paling atas saat ini adalah 'Y'.


5. isEmpty (Cek Kosong atau Tidak)

Mengecek apakah stack masih memiliki elemen.

isEmpty = not bool(stack)


6. Size (Jumlah Elemen)

Menghitung berapa banyak elemen yang tersisa.

len(stack)


Hasil Eksekusi

Stack: ['X', 'Y', 'Z']
Pop: Z
Peek: Y
isEmpty: False
Size: 2


Kesimpulan

Stack di Python dapat dibuat menggunakan list.

Prinsip kerjanya adalah LIFO (Last In, First Out).

Operasi dasar pada Stack:

append() → menambah data (push)

pop() → menghapus data teratas (pop)

stack[-1] → melihat data teratas (peek)


Struktur data ini cocok digunakan untuk fitur undo, navigasi halaman (back), dan proses yang membutuhkan urutan terbalik.



Implementasi Stack di Python

Di contoh ini aku nunjukin cara kerja struktur data Stack di Python pakai list biasa. Stack sendiri punya prinsip LIFO (Last In, First Out), jadi data yang terakhir masuk nanti yang keluar duluan.


Kode Program

stack = []

# Push
stack.append('X')
stack.append('Y')
stack.append('Z')
print("Stack:", stack)

# Pop
removed = stack.pop()
print("Pop:", removed)

# Peek
top = stack[-1]
print("Peek:", top)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)

# Size
print("Size:", len(stack))



Penjelasan

1. Inisialisasi Stack
Pertama, aku buat list kosong yang bakal dipakai sebagai stack.


2. Push (Tambah Data)
Aku masukin beberapa data ke bagian paling atas stack pakai append().
Setelah ditambah, isi stack jadi ['X', 'Y', 'Z'].


3. Pop (Hapus Data Teratas)
pop() dipakai buat ngambil data paling atas. Di sini yang keluar adalah 'Z'.


4. Peek (Lihat Data Teratas)
Pakai stack[-1] buat lihat isi paling atas tanpa hapus datanya. Hasilnya 'Y'.


5. isEmpty (Cek Kosong atau Tidak)
Di sini aku cek apakah stack masih ada isinya atau ga.


6. Size (Jumlah Data)
len(stack) dipakai buat ngecek jumlah elemen yang tersisa.




Hasil Eksekusi

Stack: ['X', 'Y', 'Z']
Pop: Z
Peek: Y
isEmpty: False
Size: 2


Kesimpulan

Stack di Python gampang dibuat cukup pakai list.

Prinsip kerjanya LIFO, jadi data yang paling baru masuk nanti yang keluar duluan.

Operasi pentingnya ada push, pop, sama peek.

Stack cocok dipakai buat fitur undo, navigasi halaman, dan berbagai proses yang butuh urutan terbalik.
