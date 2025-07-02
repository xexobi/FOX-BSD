# 📄 Arsitektur Spesifik BSD - Penjelasan File

Direktori ini berisi file-file spesifik untuk arsitektur tertentu (seperti i386, pmax, dll) dalam sistem kernel BSD. File-file ini menangani bootstrapping, manajemen memori, penanganan interrupt, debugging kernel, dan konfigurasi perangkat.

---

## 🧠 Manajemen Memori & Virtual Memory

- **mem.c** — Driver untuk perangkat `/dev/mem` dan `/dev/kmem`, memungkinkan akses langsung ke memori fisik/virtual dari ruang pengguna (biasanya hanya untuk debugging).
- **pmap.c** — Abstraksi arsitektur untuk manajemen *Page Table* dan pemetaan virtual memory ke physical memory.
- **vm_machdep.c** — Implementasi fungsi manajemen virtual memory yang spesifik untuk arsitektur, seperti `cpu_fork()` dan `pagemove()`.
- **pte.h** — Header untuk struktur *Page Table Entries* dan makro-makro yang terkait.

---

## ⚙️ Bootstrapping & Mesin

- **machdep.c** — Entry point awal sistem dari kode C. Menginisialisasi sistem, menangani boot flags, interrupt controller, setup memori, dan CPU.
- **locore.s** — Kode assembly low-level yang melakukan inisialisasi CPU, stack awal, dan memanggil `machdep()` dari C.
- **trap.c** — Penanganan exception, trap, dan interrupt dari CPU. Fungsi seperti `trap()`, `page_fault()`, dsb.
- **genassym.c** — Menghasilkan file header `assym.h` dengan offset simbol dari C untuk digunakan dalam assembly (`locore.s`).

---

## 🖥️ Konsol & I/O

- **cons.c**, **cons.h** — Implementasi konsol kernel (TTY, keyboard, serial). Menangani input/output awal sebelum subsistem terminal lengkap tersedia.
- **dkbad.c** — Menyediakan dukungan untuk bad sector table (`bad144`) pada hard disk.
- **swapgeneric.c** — Mengatur partisi swap dan root device saat boot, berdasarkan konfigurasi default atau input dari pengguna.

---

## 🛠️ Konfigurasi Kernel

- **conf.c** — Tabel konfigurasi device. Memetakan nomor major ke driver untuk block dan character device.
- **autoconf.c** — Prosedur autokonfigurasi perangkat saat booting. Mendata perangkat, memetakan driver, dan menginisialisasi perangkat aktif.
- **sys_machdep.c** — Implementasi syscall `machdep()` yang digunakan untuk operasi sistem spesifik arsitektur.

---

## 🐞 Debugging Kernel (KGDB)

- **kgdb_glue.c** — "Glue" layer yang menghubungkan kode kernel dengan `kgdb` (GNU Kernel Debugger).
- **kgdb_stub.c** — Stub debugger yang berjalan di dalam kernel, memungkinkan komunikasi dengan GDB melalui serial port.
- **kgdb_proto.h** — Header file untuk protokol komunikasi antara kernel dan GDB.

---

## 🌐 Jaringan

- **in_cksum.c** — Fungsi utilitas untuk menghitung Internet checksum (digunakan untuk IP, TCP, UDP header). Dioptimalkan untuk kecepatan.

---

## 📦 Lain-lain

- **README** — Dokumentasi deskriptif isi direktori ini.
- **tags** — File indeks yang dihasilkan oleh `ctags` untuk navigasi kode.

---

## 📝 Catatan

File-file ini adalah bagian penting dari proses boot awal, setup sistem, dan interaksi langsung dengan perangkat keras. Mereka hanya ada pada direktori `sys/arch/<machine>/`, dan spesifik untuk masing-masing arsitektur CPU.


