# Penjelasan File-File Kernel BSD

### init_main.c
Fungsi main() dari kernel â€” titik awal eksekusi kernel setelah bootloader.

### Makefile
Makefile untuk menyusun semua bagian di direktori ini.

### tty_tb.c
Dukungan untuk tablet (tablet bits/graphics terminal â€“ kuno).

### init_sysent.c
Tabel syscall â†’ fungsi.

### makesyscalls.sh
Script pembuat kode syscall otomatis.

### tty_tty.c
Device /dev/tty.

### kern_acct.c
Akuntansi penggunaan sumber daya proses.

### Make.tags.inc
Untuk sistem ctags/etags.

### uipc_domain.c
Register protokol jaringan (inet, unix, route, dll.).

### kern_clock.c
Clock tick handler (interrupt-driven scheduler).

### subr_autoconf.c
Autoconfigurasi perangkat saat boot.

### uipc_mbuf.c
Manajemen mbuf (struktur data utama untuk jaringan).

### kern_descrip.c
Manajemen file descriptor.

### subr_log.c
Logging kernel.

### uipc_proto.c
Helper protocol jaringan.

### kern_exec.c
Menjalankan program baru dalam proses (execve()).

### subr_prf.c
Print/formatting (versi printf di kernel).

### uipc_socket2.c
Helper untuk socket.

### kern_exit.c
Terminasi proses (exit()).

### subr_prof.c
Profiling (statistik eksekusi).

### uipc_socket.c
Implementasi socket.

### kern_fork.c
Kode untuk membuat proses (fork()).

### subr_rmap.c
Resource map allocator (untuk subsistem kecil, kuno).

### uipc_syscalls.c
Syscall socket(), bind(), listen(), dsb.

### kern_ktrace.c
Kernel tracing system (debug proses).

### subr_xxx.c
Kode generik/placeholder.

### uipc_usrreq.c
Permintaan user space terhadap socket.

### kern_lock.c
Implementasi kernel locking (mutex/semaphore).

### syscalls.c
Generated syscall table.

### vfs_bio.c
Buffer I/O.

### kern_malloc.c
Alokasi memori kernel (malloc(), free()).

### syscalls.conf
Konfigurasi syscall untuk pembuatan otomatis.

### vfs_cache.c
Cache nama file/path.

### kern_physio.c
Raw device I/O (misal disk access langsung).

### syscalls.master
Daftar syscall mentah.

### vfs_cluster.c
Cluster I/O (untuk optimisasi baca/tulis blok besar).

### kern_proc.c
Struktur dan daftar proses (struct proc).

### sys_generic.c
Dispatcher syscall umum.

### vfs_conf.c
Konfigurasi filesystem yang tersedia.

### kern_prot.c
Proteksi proses dan akses.

### sys_process.c
Dukungan debugging user-level (mis. ptrace()).

### vfs_init.c
Inisialisasi subsistem VFS.

### kern_resource.c
Manajemen sumber daya proses (limitasi ulimit).

### sys_socket.c
Syscall socket layer.

### vfs_lookup.c
Pencarian nama file di filesystem.

### kern_sig.c
Penanganan sinyal (signal handling).

### tags
Untuk sistem ctags/etags.

### vfs_subr.c
Fungsi bantuan VFS (virtual filesystem).

### vfs_syscalls.c
Implementasi syscall untuk filesystem.

### vfs_vnops.c
Virtual node operations â€” abstraksi file ops.

### vnode_if.sh
Script untuk menghasilkan vnode_if.c.

### kern_subr.c
Helper/utility untuk subsistem kernel.

### tty.c
Driver terminal (tty).

### tty_compat.c
Kompatibilitas dengan terminal lama.

### tty_conf.c
Konfigurasi terminal.

### tty_pty.c
Pseudoterminal.

### tty_subr.c
Utility/penunjang untuk tty subsystem.

