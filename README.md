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
