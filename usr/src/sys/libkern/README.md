
# BSD Kernel - Direktori libkern

Direktori ini berisi pustaka fungsi dasar (`libkern`) yang digunakan oleh kernel BSD.
Fungsi-fungsi di sini biasanya menggantikan fungsi `libc` yang tidak dapat digunakan di dalam kernel.

---

## 📌 Fungsi Operasi Bilangan 64-bit (quad/di3)

Digunakan untuk mendukung operasi `long long` (64-bit) pada arsitektur 32-bit:

- `adddi3.c`, `subdi3.c`, `muldi3.c`, `divdi3.c`, `moddi3.c`, `udivdi3.c`, `umoddi3.c`  
  ➤ Operasi aritmatika dasar bilangan 64-bit signed dan unsigned.

- `anddi3.c`, `iordi3.c`, `xordi3.c`, `notdi2.c`  
  ➤ Operasi logika bitwise bilangan 64-bit.

- `negdi2.c`  
  ➤ Negasi bilangan 64-bit.

- `cmpdi2.c`, `ucmpdi2.c`  
  ➤ Komparasi bilangan 64-bit signed dan unsigned.

- `ashldi3.c`, `ashrdi3.c`, `lshldi3.c`, `lshrdi3.c`  
  ➤ Operasi pergeseran bit (shift) terhadap bilangan 64-bit.

- `qdivrem.c`  
  ➤ Kombinasi pembagian dan sisa bagi (quotient dan remainder).

---

## 📌 Utilitas String dan Memori

Fungsi-fungsi pengganti `libc` untuk operasi dasar string:

- `strcat.c`, `strcpy.c`, `strncpy.c`  
  ➤ Operasi penyalinan dan penggabungan string.

- `strcmp.c`, `strlen.c`  
  ➤ Komparasi string dan panjang string.

- `rindex.c`  
  ➤ Mencari karakter terakhir dalam string.

- `bcmp.c`  
  ➤ Bandingkan dua blok memori (binary compare).

- `locc.c`, `scanc.c`, `skpc.c`  
  ➤ Pencarian karakter dalam blok byte/memori.

---

## 📌 Fungsi Pendukung Kernel

- `ffs.c`  
  ➤ Find First Set – mencari bit pertama yang aktif dalam integer.

- `random.c`  
  ➤ Fungsi generator angka acak sederhana.

- `mcount.c`  
  ➤ Digunakan untuk profiling fungsi (`gprof`), mencatat setiap kali fungsi dipanggil.

---

## 📌 Header dan Build Tools

- `quad.h`  
  ➤ Definisi tipe `quad_t` untuk bilangan 64-bit dan macro pendukung.

- `libkern.h`  
  ➤ Header utama fungsi-fungsi `libkern`.

- `Makefile`  
  ➤ Instruksi untuk kompilasi pustaka `libkern`.

- `tags`  
  ➤ File navigasi simbol sumber (ctags).

- `sparc/`, `obj/`  
  ➤ Subdirektori arsitektur dan file object (bisa jadi hasil build).

---

Fungsi-fungsi ini memungkinkan kernel BSD untuk memiliki fungsi-fungsi fundamental
tanpa mengandalkan pustaka userland seperti `libc`, menjadikan sistem lebih stabil, portabel, dan efisien.


