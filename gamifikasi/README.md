# Konsep Gamifikasi — OWL Learning

Perancangan sistem gamifikasi untuk platform e-learning OWL di PT Krakatau Posco. Gamifikasi dirancang sebagai **fitur yang melekat pada alur belajar** — bukan menu terpisah — agar peserta termotivasi belajar rutin dan menyelesaikan materi sampai tuntas.

**Status:** konsep selesai disusun (November 2026); implementasi ke dalam kode belum dilakukan.

<!-- Setelah screenshot dimasukkan ke folder images/, hapus komentar ini.
     Nama file yang dirujuk di bawah: dashboard-gamifikasi.png, level-pohon.png,
     popup-leaderboard.png, popup-quest.png -->

## Ringkasan Konsep

- Sistem memakai satu jenis poin: **EXP**. Total EXP menentukan level dan tahap pohon peserta.
- Ada **10 level**; setiap level adalah satu tahap pertumbuhan pohon, dari Seed of Knowledge (Level 1) sampai Mighty OWL Tree (Level 10, 32.000 EXP).
- EXP didapat dari aktivitas belajar, misi harian dan mingguan, dan badge.
- **Check-in** dilakukan dengan klik tombol Check-in; satu klik terhitung satu hari check-in dan satu hari **streak**.
- Tersedia **Peti Hadiah** harian dan mingguan, serta **Streak Freeze** untuk melindungi streak peserta.
- Ada **16 badge** permanen; setiap badge memberi bonus +25 EXP dan dihitung dari data belajar peserta sejak awal (retroaktif).
- **Leaderboard mingguan** diurutkan dari EXP yang diperoleh selama minggu berjalan.

## Level & Tahap Pohon

| Level | Nama Tahap Pohon | EXP Minimal |
|---|---|---|
| 1 | Seed of Knowledge | 0 |
| 2 | First Sprout | 100 |
| 3 | Green Seedling | 250 |
| 4 | Sturdy Sapling | 500 |
| 5 | Young Tree | 1.000 |
| 6 | Lush Canopy Tree | 2.000 |
| 7 | Deep-Rooted Tree | 4.000 |
| 8 | Blossoming Tree | 8.000 |
| 9 | Fruit-Bearing Tree | 16.000 |
| 10 | Mighty OWL Tree | 32.000 |

## Cara Mendapat EXP

EXP didapat dari tiga lapis:

1. **Aktivitas dasar** — aktivitas belajar yang otomatis memberi EXP, contoh: menyelesaikan konten (+10), submit task tepat waktu (+20), menyelesaikan playlist (+40), mendapat sertifikat course (+50), check-in harian (+5).
2. **Misi** — quest harian dan mingguan memberi EXP bonus di atas EXP aktivitas dasar:
   - Harian: selesaikan 1 konten (+30), selesaikan post-test (+50), lulus post-test dengan nilai 90 atau lebih (+30), beri komentar (+10)
   - Mingguan: selesaikan 1 playlist (+200), check-in 4 hari dalam seminggu (+90)
3. **Badge** — setiap badge yang terbuka memberi +25 EXP.

## Peti Hadiah & Streak Freeze

- **Peti Harian** terbuka jika semua quest harian selesai dalam satu hari; berisi bonus EXP dan/atau Streak Freeze.
- **Peti Mingguan** terbuka jika kedua misi mingguan selesai; berisi +75 EXP dan 1 Streak Freeze.
- **Streak Freeze** adalah pelindung streak: otomatis terpakai saat peserta melewatkan 1 hari check-in, sehingga streak tidak putus. Freeze didapat dari Peti Harian atau pencapaian streak 7 hari, dan jumlahnya direset setiap bulan.

## Badge & Achievement

16 badge dikelompokkan dalam 4 kategori: **Penyelesaian** (The First, Quick Finisher, Playlist Finisher, Playlist Master, Certified, Certificate Collector), **Nilai** (Perfectionist, Quiz Master, Sharp Shooter, Top Scorer), **Konsistensi** (On Time Learner, Learning Marathon, Streak Master), dan **Pencapaian** (Milestone 10 Jam, Milestone 50 Jam, Legend Learner). Semua badge bersifat permanen dan retroaktif.

## Penempatan di LMS

- **Home:** ringkasan level, EXP, streak, dan misi harian.
- **My Learning:** tab **Learning Journey** berisi profil level dan pohon, leaderboard, badge, dan misi lengkap; detail ditampilkan sebagai pop-up (leaderboard, daftar badge, cara mendapat EXP, detail misi).

## Screenshot

![Dashboard Gamifikasi](images/dashboard-gamifikasi.png)
*Dashboard gamifikasi di tab Learning Journey*

![Level & Tahap Pohon](images/level-pohon.png)
*Jenjang 10 level tahap pertumbuhan pohon*

![Pop-up Leaderboard](images/popup-leaderboard.png)
*Pop-up leaderboard mingguan*

![Pop-up Quest](images/popup-quest.png)
*Pop-up misi harian dan mingguan*
