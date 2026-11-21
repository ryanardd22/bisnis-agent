# Draf penawaran dan bahan validasi

## Penawaran pilot Indonesia

**Perbaikan satu laporan penjualan atau operasional di Google Sheets · Rp850.000**

Jika angka laporan harus diperbaiki manual setiap minggu, Revoult merapikan satu alur dari ekspor yang sudah dipakai hingga ringkasan yang bisa dijalankan ulang. Kita menentukan satu masalah, satu sumber data, dan angka acuan sebelum mulai. Anda menerima salinan siap pakai, satu contoh hasil yang diperiksa bersama, dan panduan menjalankan ulang laporan.

Pengerjaan dua hari kerja setelah sampel bertopeng, lingkup, dan pembayaran siap. Termasuk satu revisi yang sesuai lingkup. Untuk klien langsung independen, uang muka Rp425.000 dan Rp425.000 saat hasil diterima. Untuk proyek dari marketplace, pendanaan dan penerimaan mengikuti aturan platform. Integrasi baru, migrasi sistem, dan pemeliharaan berkelanjutan diperhitungkan sebagai lingkup lain jika diperlukan.

## Pesan pertama untuk perkenalan yang disetujui

> Halo [Nama], saya [Nama founder] dari Revoult. Saya melihat [sinyal yang benar dan relevan]. Saat membuat laporan [nama laporan] dari CSV atau Google Sheets, bagian mana yang paling sering harus dibetulkan lagi?
>
> Saya menawarkan pilot Rp850.000 untuk merapikan satu alur laporan yang sudah berjalan. Jika cocok, kita gunakan contoh anonim, tentukan angka acuannya, dan saya serahkan file yang bisa dipakai ulang dalam dua hari kerja. Boleh kita cek kecocokannya selama 15 menit?

## Draf penawaran di marketplace

> Saya bisa membantu merapikan alur [masalah spesifik dari brief] dari satu [CSV/tab] ke satu tab laporan. Usulan Rp850.000 mencakup [aturan rekonsiliasi], uji dengan sampel yang sudah disamarkan, salinan hasil, dan panduan. Saya bisa serahkan dalam dua hari kerja setelah scope dan pendanaan proyek siap. Apa satu angka yang perlu cocok dengan laporan acuan untuk menerima hasilnya?

## Panduan percakapan 15 menit

1. Kapan terakhir laporan dibuat, dari mana datanya, dan berapa lama pekerjaan manualnya?
2. Kesalahan atau selisih terakhir seperti apa? Berapa kali muncul bulan ini dan keputusan apa yang tertunda?
3. Sudah mencoba laporan bawaan atau pivot? Aturan bisnis apa yang masih harus diterapkan manual?
4. Siapa pemilik laporan dan siapa yang menyetujui Rp850.000? Kapan mereka perlu hasilnya?
5. Bisa kirim 20 baris yang disamarkan beserta total acuan untuk satu periode? Setujui satu aturan, satu tab keluaran, dan satu cara mengecek hasil.

## Contoh sintetis untuk ditunjukkan

Contoh satu ekspor berisi empat baris transaksi dan satu baris refund. Acuan menggabungkan transaksi dengan ID unik yang sudah dibayar dan mengurangi refund yang sudah diproses.

| Referensi | Status | Nilai | Perlakuan |
| --- | --- | ---: | --- |
| ORD-101 | Lunas | Rp120.000 | Masuk |
| ORD-102 | Lunas | Rp80.000 | Masuk |
| ORD-102 | Duplikat ekspor | Rp80.000 | Abaikan |
| REF-103 | Refund selesai | −Rp25.000 | Kurangi |
| ORD-104 | Belum dibayar | Rp50.000 | Abaikan |

Penjumlahan mentah Rp305.000. Hasil rekonsiliasi Rp175.000, terdiri dari penjualan lunas Rp200.000 dikurangi refund Rp25.000. Satu baris duplikat dan satu baris belum dibayar dikeluarkan. Angka ini ilustrasi dari data fiktif.

## Konfirmasi lingkup sebelum mulai

| Butir | Isi bersama calon pembeli |
| --- | --- |
| Laporan dan tujuan | [Nama laporan, pemakai, frekuensi dan keputusan] |
| Bahan uji | [CSV atau satu tab, 20 baris disamarkan, satu periode] |
| Aturan dan keluaran | [Satu aturan rekonsiliasi, satu tab, total yang harus cocok] |
| Penerimaan | [Cocok dengan jumlah acuan, input yang sama memberi hasil sama, panduan berhasil diikuti] |
| Harga dan metode | [Rp850.000, uang muka atau milestone sesuai kanal, jadwal penerimaan] |

Catat menit pengerjaan manual dari satu run berdasarkan pengamatan atau keterangan pelanggan. Ulangi dengan sampel dan bedakan hasil terukur dari perkiraan. Gunakan salinan dengan akses yang disetujui dan minta pelanggan mengekspor sampel sendiri.

## Draf proposal cadangan internasional

> I can take [named failing flow] as a standalone US$150 milestone. I’ll reproduce it in staging, deliver a reviewable patch and one regression check, and include a short handoff within two business days of funded scope and approved staging access. What should happen after [specific trigger], and can we reproduce the failure with a test account?
