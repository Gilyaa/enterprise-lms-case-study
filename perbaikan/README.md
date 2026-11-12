# Perbaikan & Penyesuaian

Perbaikan pada modul OWL yang sudah berjalan, di luar pengembangan fitur baru.

## 1. Status Final Hasil Assessment Saat Waktu Habis

**Modul:** Assessment

**Masalah:** Ketika peserta sedang memproses assessment dan waktu pengerjaan habis, status `final` pada data hasil assessment (`assessment_results`) belum berubah menjadi `true`, sehingga hasil peserta berpotensi dianggap belum selesai oleh sistem.

**Perbaikan:** Ditambahkan mekanisme auto-finalize berupa command `assessment:finalize-expired-drafts` yang memeriksa draft attempt yang masih aktif (`final = 0`) dan memfinalkan draft yang durasi pengerjaan atau periode aksesnya sudah habis, sehingga nilai `final` pada `assessment_results` menjadi `true`. Tampilan sisi peserta juga disesuaikan agar tidak lagi menampilkan draft yang sudah tidak berlaku (draft fallback).

**Hasil:** Sudah diperbaiki dan dipastikan kembali (terverifikasi 9 November 2026): assessment yang kehabisan waktu kini tercatat sebagai selesai dengan `final = true`.

<!-- Tambahkan screenshot di folder images/ bila ada, lalu rujuk di sini,
     contoh: ![Assessment](images/assessment.png) -->
