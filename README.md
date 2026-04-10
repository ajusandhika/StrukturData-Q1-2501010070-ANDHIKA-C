# 1. Karakteristik Memori dan Akses Data

Array memiliki keunggulan dalam hal akses data karena disimpan pada **memori yang berurutan (kontinu)**. Untuk mengakses elemen, komputer hanya menggunakan indeks sehingga waktu akses menjadi **O(1)**.

Sebaliknya, Singly Linked List tidak disimpan secara berurutan di memori. Setiap node memiliki pointer ke node berikutnya. Untuk mengakses data tertentu, harus dilakukan traversal dari awal sehingga membutuhkan waktu **O(n)**.

---

# 2. Analisis Efisiensi Operasi Manipulasi

Linked List lebih unggul dalam operasi penyisipan dan penghapusan data.

* **Array**: perlu menggeser elemen → **O(n)**
* **Linked List**: hanya ubah pointer → **O(1)** (jika posisi diketahui)

Linked List cocok digunakan ketika:

* Data sering berubah
* Ukuran data dinamis

---

# 3. Konsep Doubly Linked List

Doubly Linked List memiliki:

* Data
* Pointer ke next
* Pointer ke prev

Kelebihan:

* Bisa traversal dua arah

Kekurangan:

* Lebih boros memori
* Lebih kompleks

---

# 4. Mekanisme Circular Linked List

Circular Linked List adalah Linked List di mana node terakhir menunjuk kembali ke head.

Ciri khas:

* Tidak ada NULL
* Bersifat melingkar

Contoh penggunaan:

* Sistem **Round Robin**

---

# 5. Array Dinamis di Python

Python list menggunakan Dynamic Array.

Saat penuh:

1. Membuat array baru lebih besar
2. Copy data lama
3. Tambahkan elemen baru

Secara rata-rata tetap **O(1)** (amortized).

---

# 💻 IMPLEMENTASI KODE

## 🔹 1. Array (Python List)

```python
data = [10, 20, 30, 40, 50]

# Akses elemen
print("Elemen index ke-2:", data[2])

# Tambah data
data.append(60)
print("Setelah append:", data)

# Hapus data
data.remove(30)
print("Setelah hapus:", data)
```

---

## 🔹 2. Singly Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)

        if not self.head:
            self.head = new_node
            return

        temp = self.head
        while temp.next:
            temp = temp.next

        temp.next = new_node

    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

# Testing
ll = SinglyLinkedList()
ll.append(10)
ll.append(20)
ll.append(30)
ll.display()
```

---

## 🔹 3. Doubly Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)

        if not self.head:
            self.head = new_node
            return

        temp = self.head
        while temp.next:
            temp = temp.next

        temp.next = new_node
        new_node.prev = temp

    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" <-> ")
            temp = temp.next
        print("None")

# Testing
dll = DoublyLinkedList()
dll.append(1)
dll.append(2)
dll.append(3)
dll.display()
```

---

## 🔹 4. Circular Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class CircularLinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)

        if not self.head:
            self.head = new_node
            new_node.next = self.head
            return

        temp = self.head
        while temp.next != self.head:
            temp = temp.next

        temp.next = new_node
        new_node.next = self.head

    def display(self):
        temp = self.head
        if not temp:
            return

        while True:
            print(temp.data, end=" -> ")
            temp = temp.next
            if temp == self.head:
                break
        print("(kembali ke head)")

# Testing
cll = CircularLinkedList()
cll.append(5)
cll.append(10)
cll.append(15)
cll.display()
```

---
