# Fitur My Task — OWL Learning

Fitur manajemen tugas (task) yang saya bangun untuk platform e-learning OWL di PT Krakatau Posco. Melalui fitur ini, admin dapat memberikan tugas kepada peserta di dalam alur belajar yang sudah ada, dan peserta dapat melihat, mengerjakan, dan mengumpulkan tugasnya dari halaman My Task.

_Dokumentasi ini mengikuti kondisi project per 12 November 2026._

<!-- Setelah screenshot dimasukkan ke folder images/, hapus komentar ini.
     Nama file yang dirujuk di bawah: dashboard-admin.png, form-buat-task.png,
     dashboard-user.png, global-task.png, review-submissions.png -->

## Latar Belakang

Sebelum fitur ini ada, pemberian tugas kepada peserta belum terwadahi di dalam LMS. My Task mengintegrasikan tugas langsung ke struktur belajar OWL: task ditempatkan pada materi yang sedang dipelajari peserta, sehingga konteks tugasnya selalu jelas.

## Cara Kerja

### Penempatan Task (Placement)

Task dapat ditempatkan pada tiga jenis induk:

- **Playlist**
- **Content**
- **Offline Training** (penempatan tersedia; data offline training belum terhubung ke project, sehingga pilihannya belum aktif)

Selain itu, task juga dapat dibuat **tanpa penempatan (standalone)** untuk kebutuhan tugas yang tidak terikat materi tertentu.

Di sisi peserta, task yang sudah diterbitkan (published) muncul di halaman My Task setelah peserta membuka induknya (playlist/konten terkait). Task pada playlist juga dapat dibuka (unlock) oleh peserta dari halaman playlist.

### Task Group

Task dapat dikelompokkan ke dalam **grup** (judul + deskripsi) agar pengelolaan task yang jumlahnya banyak lebih rapi. Grup yang dihapus masuk ke trash (soft delete) dan dapat dipulihkan.

### Tipe Task

Terdapat 5 tipe task, dan form pembuatan task menyesuaikan isinya mengikuti tipe yang dipilih:

1. **File Submission** — peserta mengumpulkan file sebagai jawaban. Admin mengatur tipe file yang diizinkan, ukuran maksimal per file, dan opsi alternatif berupa link Google Drive dari peserta.
2. **Course Assignment** — peserta membuka course yang ditautkan. Course di dalam LMS menandai task otomatis selesai saat progress course mencapai 100%, sedangkan course berupa link eksternal ditandai selesai secara manual oleh peserta ("Mark as Complete").
3. **Survey** — peserta mengisi form survey yang sudah ada di LMS; admin memilih survey tujuan dari dropdown.
4. **Essay / Reflection** — peserta menjawab dalam teks panjang; admin menilai secara manual.
5. **Action Plan** — form builder ala Google Form: jawaban singkat, paragraf, pilihan ganda (multiple choice), checkbox dengan batas minimal/maksimal pilihan, dropdown, file, skala, dan rating bintang. Admin meninjau jawaban secara manual.

### Global Task: Kode Akses, QR Code, dan Trash

- Task standalone dapat dilindungi **kode akses** yang diketik manual oleh admin (maksimal 12 karakter, unik)
- Peserta membuka task standalone dengan tiga cara: memasukkan kode akses, membuka link redeem, atau link bertanda tangan (signed URL)
- Task dibagikan melalui **QR code**; mengganti kode akses otomatis membatalkan link/QR lama
- Penghapusan task bersifat **soft delete**: task masuk ke **Trash** dan dapat di-**Restore** atau dihapus permanen (**Delete forever**). Trash terpadu menampilkan filter tipe, dan mendukung aksi massal (pilih semua, restore/hapus permanen sekaligus)

## Tampilan Admin

- Dashboard Task Management menampilkan task berdasarkan wadahnya (induk/grup), dilengkapi pencarian dan dropdown item yang dapat dicari (AJAX)
- Form pembuatan task: pilihan penempatan, tipe task, dan pengaturan pertanyaan yang menyesuaikan tipe
- Aksi per baris tabel dirangkum dalam satu dropdown "...", mengikuti pola halaman Assessment
- **Review submission:** daftar pengumpulan dilengkapi filter cepat (semua / perlu ditinjau / disetujui / ditolak) dan jendela review (modal) untuk menilai per peserta. Admin dapat **menyetujui (approve)**, **menolak (reject)**, atau **meminta peserta mengumpulkan ulang (request resubmit)**; submission yang diminta ulang ditandai dengan badge revisi di sisi peserta
- **Preview dokumen** langsung dari halaman review, termasuk file presentasi (PPT/PPTX) dan PDF
- **Ekspor hasil:** submission dapat diunduh sebagai Excel/CSV, dan seluruh lampiran peserta dapat diunduh sekaligus sebagai ZIP

## Tampilan Peserta

- Halaman My Task berisi ringkasan dan daftar task peserta, dikelompokkan per kategori dan dilengkapi filter cepat Content Playlist
- Setelah mengumpulkan task, peserta menerima pop-up konfirmasi sukses
- Task dari course yang terhubung menampilkan status penyelesaiannya secara otomatis ("Course completed")
- Task yang diminta admin untuk dikumpulkan ulang tampil dengan penanda revisi

## Screenshot

![Dashboard Task Management (Admin)](images/dashboard-admin.png)
*Dashboard Task Management di sisi admin*

![Form Pembuatan Task](images/form-buat-task.png)
*Form pembuatan task dengan pilihan penempatan dan tipe task*

![Halaman My Task Peserta](images/dashboard-user.png)
*Halaman My Task di sisi peserta*

![Global Task & Kode Akses](images/global-task.png)
*Task mandiri (standalone) dengan kode akses dan QR code*

![Review Submission](images/review-submissions.png)
*Halaman review submission peserta di sisi admin*
