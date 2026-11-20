# Tugas 4 — Flowchart "Sistem Deteksi Arah"

## Deskripsi Tugas
Menggambar diagram alir (*flowchart*) menggunakan simbol standar untuk memodelkan logika kendali **Sistem Deteksi Arah** antena berbasis pembacaan sinyal *Analog-to-Digital Converter* (ADC).

## Daftar Berkas
* [`Flowchart_Sistem_Deteksi_Arah.png`](./Flowchart_Sistem_Deteksi_Arah.png) — Gambar diagram alir resolusi tinggi.
* [`flowchart_sistem_deteksi_arah.mmd`](./flowchart_sistem_deteksi_arah.mmd) — Kode sumber diagram berbasis Mermaid.js.

## Penjelasan Alur Algoritma
1. **Inisialisasi (`MULAI` -> `PENTOKAN KE TEPI` -> `ISI REGISTER DATA LEVEL DENGAN 0`):** Antena digerakkan ke batas posisi awal (tepi) dan nilai register penyimpan sinyal tertinggi di-reset ke `0`.
2. **Akuisisi Data (`BACA LEVEL SINYAL DARI ADC`):** Sistem membaca intensitas sinyal masuk melalui kanal ADC.
3. **Evaluasi Sinyal Maksimum (`ADC > REGISTER`):**
   * Jika **YA**, nilai pembacaan ADC terbaru disimpan ke dalam register (`ISIKAN DATA ADC KE REGISTER`) dan koordinat posisi antena saat itu dicatat (`CATAT POSISI ANTENA`).
   * Jika **TIDAK**, nilai register dan posisi terbaik sebelumnya dipertahankan.
4. **Pengecekan Batas Mekanik (`APA SUDAH MENTOK ?`):**
   * Jika **TIDAK**, antena digerakkan satu langkah (`GERAKAN ANTENA SATU STEP`) dan proses kembali membaca level sinyal ADC.
   * Jika **YA**, pemindaian selesai; antena diputar kembali (`PUTAR KE KIRI`) untuk mengarah ke koordinat sinyal maksimum yang telah dicatat (`CARI POSISI TERBAIK`), lalu proses berakhir (`SELESAI`).
