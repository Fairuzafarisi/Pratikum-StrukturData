```markdown
# 🔗 Implementasi Linked List di Python

Program ini menunjukkan contoh sederhana **struktur data Linked List (singly linked list)** menggunakan list di Python. Linked List bekerja dengan prinsip **pointer/reference** — setiap node menyimpan data dan pointer ke node berikutnya.

---

## 📘 Kode Program

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_first(self, data):
        node = Node(data, self.head)
        self.head = node

    def insert_at_last(self, data):
        if self.head is None:
            self.head = Node(data)
            return
        
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        
        node = Node(data)
        node_sekarang.next = node

    def insert_at(self, index, data):
        if index < 0 or index > self.length() - 1:
            print("index tidak valid")
        elif index == 0:
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head
            
            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next
            
            node = Node(data, node_sekarang.next)
            node_sekarang.next = node

    def remove_first(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        else:
            self.head = self.head.next

    def remove_last(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        elif self.head.next is None:
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head
            
            while node_sekarang.next:
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next
            
            node_sebelumnya.next = None

    def remove_at(self, index):
        if index < 0 or index > self.length():
            print("index tidak valid")
        elif index == 0:
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head
            
            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next
            
            node_sekarang.next = node_sekarang.next.next

    def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ''
            node_sekarang = self.head
            
            while node_sekarang:
                text_print += str(node_sekarang.data) + " -> "
                node_sekarang = node_sekarang.next
            
            print(text_print)

    def length(self):
        urutan = 0
        data_sekarang = self.head
        
        while data_sekarang:
            data_sekarang = data_sekarang.next
            urutan += 1
        
        return urutan

# Membuat linked list
ll = LinkedList()

# Insert
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "anggur")

# Remove
ll.remove_first()
ll.remove_last()
ll.remove_at(1)
ll.remove_at(1)

# Print
ll.print()
print(ll.length())
```

---

## 📖 Penjelasan

### 1. **Inisialisasi Node dan LinkedList**
Membuat class `Node` untuk merepresentasikan setiap elemen dalam linked list, dan class `LinkedList` untuk mengelola seluruh list:

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer

class LinkedList:
    def __init__(self):
        self.head = None
```

### 2. **Insert at First (Menambah Data di Awal)**
Menambahkan elemen baru di awal linked list menggunakan `insert_at_first()`:

```python
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
```

Setelah bagian ini, isi linked list: `['manggis', 'mangga', 'jeruk']`

### 3. **Insert at Last (Menambah Data di Akhir)**
Menambahkan elemen baru di akhir linked list menggunakan `insert_at_last()`:

```python
ll.insert_at_last("apel")
```

Isi linked list sekarang: `['manggis', 'mangga', 'jeruk', 'apel']`

### 4. **Insert at Index (Menambah Data di Posisi Tertentu)**
Menambahkan elemen pada index tertentu menggunakan `insert_at()`:

```python
ll.insert_at(2, "anggur")
```

Isi linked list sekarang: `['manggis', 'mangga', 'anggur', 'jeruk', 'apel']`

### 5. **Remove First (Menghapus Data Pertama)**
Menghapus elemen pertama dengan `remove_first()`:

```python
ll.remove_first()
```

Elemen `'manggis'` dihapus. Isi linked list: `['mangga', 'anggur', 'jeruk', 'apel']`

### 6. **Remove Last (Menghapus Data Terakhir)**
Menghapus elemen terakhir dengan `remove_last()`:

```python
ll.remove_last()
```

Elemen `'apel'` dihapus. Isi linked list: `['mangga', 'anggur', 'jeruk']`

### 7. **Remove at Index (Menghapus Data di Posisi Tertentu)**
Menghapus elemen pada index tertentu menggunakan `remove_at()`:

```python
ll.remove_at(1)  # Menghapus 'anggur'
ll.remove_at(1)  # Menghapus 'jeruk'
```

Isi linked list sekarang: `['mangga']`

### 8. **Print (Menampilkan Linked List)**
Menampilkan seluruh isi linked list:

```python
ll.print()
```

### 9. **Length (Menghitung Jumlah Elemen)**
Menghitung berapa banyak elemen yang tersisa:

```python
print(ll.length())
```

---

## 🎯 Hasil Eksekusi

```
mangga -> 
1
```

**Penjelasan:**
- Setelah semua operasi insert dan remove, linked list hanya tersisa satu elemen yaitu `'mangga'`
- Panjang linked list adalah `1`

---

## 💡 Kesimpulan

- **Linked List** di Python bisa dibuat dengan menggunakan class `Node` dan class `LinkedList`
- **Operasi dasar:**
  - `insert_at_first()` → menambah data di awal
  - `insert_at_last()` → menambah data di akhir
  - `insert_at(index, data)` → menambah data di posisi tertentu
  - `remove_first()` → menghapus data pertama
  - `remove_last()` → menghapus data terakhir
  - `remove_at(index)` → menghapus data di posisi tertentu
  - `print()` → menampilkan seluruh linked list
  - `length()` → menghitung jumlah elemen
- Struktur ini berguna untuk simulasi **struktur data dinamis** yang membutuhkan operasi insert dan delete yang efisien di berbagai posisi

---

## 📌 Catatan

- Linked List berbeda dengan array/list biasa karena tidak menyimpan data secara berurutan di memori
- Setiap node menyimpan **data** dan **pointer** ke node berikutnya
- Operasi insert/delete di awal linked list lebih cepat dibanding array (O(1) vs O(n))
```

---

Penjelasan cara membuat README seperti ini:

1. **Heading (Judul):**
   - `#` = heading besar
   - `##` = heading sedang
   - `###` = heading kecil

2. **Bold (Tebal):**
   - `**teks**` = **teks tebal**

3. **Italic (Miring):**
   - `*teks*` = *teks miring*

4. **Code Block:**
   - ````python` untuk memulai code block Python
   - ```` untuk menutup code block

5. **Inline Code:**
   - `` `kode` `` = `kode`

6. **Horizontal Line:**
   - `---` = garis pemisah

7. **Emoji:**
   - Bisa pakai emoji langsung: 🔗 📘 💡 🎯

8. **Bullet Points:**
   - `-` atau `*` di awal baris
