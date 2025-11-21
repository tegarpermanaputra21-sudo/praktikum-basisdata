# 📘 Rangkuman Modul Praktikum Basis Data (Bab 1–2)

Repository ini berisi rangkuman materi dari **Modul Praktikum Basis Data – MySQL** untuk **Bab 1 dan Bab 2**, mencakup dasar perancangan basis data menggunakan ERD serta perintah dasar DDL pada MySQL.

---

## 📄 Sumber Modul

Modul asli dapat diakses melalui file berikut:

[📘 MODUL PRAKTIKUM BASIS DATA.pdf](sandbox:/mnt/data/MODUL%20PRAKTIKUM%20BASIS%20DATA.pdf)

---

# 📚 BAB 1 — Konversi ER Diagram ke Skema Relasi

Bab ini membahas cara mengonversi *Entity Relationship Diagram (ERD)* menjadi **skema relasi**, kemudian diterjemahkan menjadi **tabel fisik** dalam database.

---

## 🔑 Konsep Utama

### **1. Entitas (Entity)**
Objek nyata yang dapat diidentifikasi.  
➡️ Menjadi **tabel**.

### **2. Atribut (Attribute)**
Karakteristik dari entitas.  
➡️ Menjadi **kolom**.

### **3. Primary Key (PK)**
Atribut unik untuk membedakan tiap record.  
➡️ Tetap menjadi PK.

### **4. Relasi (Relationship)**
Hubungan antar entitas.  
➡️ Menghasilkan **Foreign Key** atau **tabel relasi**.

### **5. Kardinalitas**
Jenis hubungan:
- **1 — 1**
- **1 — N**
- **N — M**

---

# 🔄 Aturan Konversi ERD → Relasi

### **1. Entitas Kuat → Tabel**
- Semua atribut menjadi kolom
- PK tetap sama

### **2. Atribut Komposit → Dipecah**
Contoh:  
`Alamat → (jalan, kota, provinsi)`

### **3. Atribut Multivalue → Tabel Baru**
Karena satu entitas bisa memiliki banyak nilai.

### **4. Entitas Lemah**
- Menjadi tabel baru
- PK gabungan (PK entitas kuat + atribut lemah)

### **5. Relasi 1 — 1**
FK ditempatkan pada salah satu tabel (biasanya yang lebih lemah).

### **6. Relasi 1 — N**
FK ditempatkan pada sisi **N**.

### **7. Relasi 1 — N dengan Atribut Relasi**
Harus menjadi **tabel baru**.

### **8. Relasi N — M**
Selalu menjadi **tabel relasi** yang berisi:
- FK entitas A  
- FK entitas B  
- Atribut relasi (jika ada)

### **9. Unary Relationship**
Relasi dalam satu entitas:
- 1–1 → FK dalam tabel
- N–M → tabel relasi tambahan

### **10. Ternary Relationship**
3 entitas → menghasilkan:
- 3 tabel entitas
- 1 tabel relasi

### **11. Generalisasi / Spesialisasi (ISA)**
Dua pendekatan:
- Superclass + Subclass  
- Hanya Subclass (menggabungkan atribut)

### **12. Agregasi**
Relasi kompleks → tabel relasi tambahan.

---

## 🧪 Studi Kasus: Skema Apotik

Konversi ERD Apotik menghasilkan beberapa tabel, di antaranya:

- pasien  
- dokter  
- resep  
- detail_resep  
- obat  
- kategori_obat  
- pegawai  
- pembayaran  
- retur  

---

# 📚 BAB 2 — Pengantar Basis Data & DDL MySQL

Bab ini membahas pengenalan database, DBMS, dan perintah dasar SQL untuk pengelolaan database.

---

## 🔑 Konsep Dasar

### **Basis Data**
Kumpulan data terorganisir agar mudah diakses.

### **DBMS**
Software untuk mengelola database, contoh:
- MySQL  
- PostgreSQL  
- MariaDB  
- Oracle  
- SQL Server  

### **MySQL**
DBMS populer:
- Open-source  
- Menggunakan SQL  
- Banyak digunakan dalam aplikasi web  

---

# 💻 Mengakses MySQL via CLI

### **Login MySQL (Windows/XAMPP)**

```bash
cd C:\xampp\mysql\bin
mysql -u root -p
