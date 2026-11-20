# Tugas 1 — Pembuatan Undangan Massal dengan Mail Merge

## Deskripsi Tugas
Membuat surat undangan resmi yang dipersonalisasi secara otomatis untuk banyak penerima dengan mengintegrasikan **Microsoft Excel** sebagai sumber data (*data source*) dan **Microsoft Word** sebagai templat dokumen utama menggunakan fitur **Mail Merge**.

* **Referensi Tutorial:** [Tips Cara Menggunakan Mail Merge di Microsoft Word (Jendela Tutorial)](https://youtu.be/8VNH7kgdQSE)

## Daftar Berkas
1. [`Data_Penerima_Undangan.xlsx`](./Data_Penerima_Undangan.xlsx) — Tabel database penerima undangan berisi kolom `No`, `Nama`, `Jabatan`, `Instansi`, `Alamat`, dan `Kota`.
2. [`Template_Undangan_Mail_Merge.docx`](./Template_Undangan_Mail_Merge.docx) — Dokumen master surat undangan berukuran A4 (Times New Roman 12 pt, spasi 1.5) dengan *merge fields* siap pakai.

## Langkah Implementasi Teknis
1. **Menyiapkan Data Sumber (Excel):** Membuat tabel dengan baris pertama sebagai judul kolom (*header*) tanpa sel yang digabung (*merged cells*).
2. **Menghubungkan Data ke Word:** Membuka tab **Mailings** -> **Select Recipients** -> **Use an Existing List**, memilih file `Data_Penerima_Undangan.xlsx`, dan memastikan kotak centang **First row of data contains column headers** aktif.
3. **Menyisipkan Merge Fields:** Menempatkan kursor pada bagian tujuan surat lalu memilih **Insert Merge Field** (`«Nama»`, `«Jabatan»`, `«Instansi»`, `«Alamat»`, `«Kota»`).
4. **Pratinjau & Penyelesaian:** Menggunakan tombol **Preview Results** untuk memverifikasi kecocokan data tiap penerima, lalu mengekspor dokumen akhir melalui **Finish & Merge**.
5. **Catatan Teknis:** File Excel sumber data harus ditutup saat dihubungkan ke Word agar tidak terkunci dalam mode *Read-Only*.
