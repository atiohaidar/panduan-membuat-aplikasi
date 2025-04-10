# Langkah-Langkah Pengembangan Aplikasi Menggunakan Bantuan AI

**PENTING:**
*   Untuk nama dari context bagusnya itu `copilot-instructions.md` di dalem folder gitub. isinya konteks nya kayak struktur foldernya kayak gimana dll 
*   Setiap tahapan dapat melibatkan beberapa kali *prompting*. Misalnya, pembuatan *requirement* bisa memerlukan lebih dari satu *prompt*, bahkan mungkin hingga 10 kali.
*   Sentuhan manusia tetap sangat penting, terutama saat masih banyak *error*.
*   Pertimbangkan aspek non-fungsional seperti keamanan, performa, skalabilitas, *accessibility*, dan *maintainability* di setiap tahapan yang relevan.
*   Jika bekerja dalam tim, kolaborasi tim sangatlah penting. Gunakan alat kolaborasi seperti Git untuk *version control*, *project management tools*, dan lakukan *code review* secara berkala.
*   Make konsep MPC kalo diperlukan
*   Kalau perlu konteks dari internet, bisa aja
[Referensi](https://youtu.be/dutyOc_cAEU?si=ZL6Xd14hY9PucOIY)

**Tips Penggunaan *Prompting*:** *Prompting* dapat dimanfaatkan di berbagai tahapan untuk membantu mempercepat dan meningkatkan kualitas pengembangan.

*   *Brainstorming* ide aplikasi.
*   Menghasilkan daftar fitur awal dan *user story*.
*   Merumuskan draf arsitektur, skema *database*, dan dokumentasi API.
*   Membuat *template code*, *mockup* UI, dan *unit test* awal.
*   Mendapatkan saran solusi untuk kendala teknis.

**Setiap kali ada pembaruan fitur, jangan lupa untuk *push* kode ke GitHub.**

## 0. Cari Ide Aplikasi
**Output:** Ide aplikasi

## 1. Tentukan *Requirement*
**Context:** Ide aplikasi

Buat berkas `requirement.md` yang berisi daftar fitur dan aturan aplikasi. Susun juga dalam bentuk *user story* dan tentukan alur aplikasi. Terus juga kalau bisa bantuknya kayak PRD (Project  Reuqirement Document) , ada FR1 FR2 dll. bentuk nya tabel, kolom nya ada "description", "user story" dan "expected behaviour". Buat juga `testplan.md` yang lebih komprehensif, mencakup berbagai jenis pengujian setidaknya untuk apa yang user butuhkan. tapi lebih baik lagi jika ingin detail seperti *unit test*. Paling minimal: *integration test*, *end-to-end test*, *performance test*, *security test*, dan *user acceptance testing* (UAT) (*automated testing*) jika memungkinkan.

**Output:** `requirement.md`, `testplan.md`

## 2. Tentukan Arsitektur Umum Aplikasi
**Context:** Berkas `requirement.md`,`testplan.md`

Tentukan teknologi yang digunakan untuk *frontend*, *backend*, dan *database*. Rancang alur data dan komunikasi antar komponen. Pertimbangkan aspek keamanan dan skalabilitas dalam arsitektur aplikasi.

**Output:** `arsitektur.md`

## 3. Tentukan Skema *Database*
**Context:** `requirement.md`, `arsitektur.md`

Rancang skema *database* secara lengkap menggunakan plantuml, termasuk hubungan antar tabel dan entitas hingga kardinalitasnya.

**Output:** `skema_database.plantuml`

## 4. Tentukan API Documentation
**Context:** `requirement.md`, `arsitektur.md`, `skema_database.plantuml`, `testplan.md`

Buat dokumentasi API untuk semua fitur yang ada. Hasilnya berupa *Postman Collection* yang dapat digunakan, termasuk *mocking* API dari Postman dengan contoh *request* dan *response*.

[Referensi Mocking API Postman](https://www.youtube.com/watch?v=fWOf0iNRcbg)

**Output:** `postman-collection.json`, *mocking* API

## Sisi *Frontend*

## 5. Tentukan Konteks Proyek *Frontend*
**Context:** `requirement.md`, `arsitektur.md`, `testplan.md`, `postman-collection.json`

Tentukan struktur *folder* proyek, paket (*package*) yang digunakan, teknologi *frontend* (misalnya *React*, *Vue*, *Angular*, *Bootstrap*, *Tailwind CSS*), gaya (*style*), penamaan *file*, aturan *changelog*, urutan pengembangan fitur, dan aturan lainnya. Pertimbangkan aspek performa, *accessibility*, dan *maintainability* aplikasi *frontend*. Gunakan Git untuk *version control*, *project management tools* untuk manajemen tugas, dan lakukan *code review* secara berkala.

Buat berkas `context_frontend.md` yang mendokumentasikan semua keputusan ini. Buat juga berkas `progress_frontend.md` yang berisi daftar tugas yang akan dikerjakan dan *checklist* progres. Di bagian bawah `progress_frontend.md`, tambahkan evaluasi progres pengerjaan, kendala, dan solusi (mirip *lesson learned*). Setiap kendala dan solusi didokumentasikan dengan judul dan deskripsi. Pastikan struktur *folder* mudah di-*maintain* dan *performance* aplikasi baik.
oh iya karena frontend bisa kita tentuin aja style nya mau kayak apa. bahkan bisa make gambar juga kayak [gini](https://youtu.be/pEEw7BvaK50?si=Bp7P2ahyx4_O53Cf)

**TIPS:** Mulai dari struktur dasar, kembangkan fitur satu per satu, langsung lakukan tes minimal unit testing,  dan *update progress*, **dan *push* kode ke GitHub**. **INGAT**, urutannya: fitur, tes, catat, *push*. Jika ada *error*, segera catat *error* tersebut. Kalau make Github Copilot. itu kita bisa nge masukin konteks nya dari link dokumentasi resmi. make #fetch terus masukin link nya. jadi bisa make versi yang ter update dari framework tersebut

**OUTPUT:** `context_frontend.md`, `progress_frontend.md`

## 6. Siapkan *Environment* Proyek *Frontend*
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`

Instal dependensi proyek, buat struktur *folder*, dan buat tes arsitektur (misalnya tes *routing* dan tampilan *frontend*). Lakukan *unit test* sederhana. Pastikan *environment* aman sebelum melanjutkan.

[Referensi Unit Test React](https://www.youtube.com/watch?v=i2MEVuInFKw)

**Catatan:** *Unit test* tidak harus selalu menggunakan React, sesuaikan dengan teknologi yang digunakan.

**OUTPUT:** `progress_frontend.md`, proyek siap digunakan, termasuk *unit test*

## 7. Kembangkan Fitur Pertama hingga Fitur ke-N
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`

Setelah proyek siap, kerjakan fitur satu per satu, jangan langsung semuanya. Mulai dengan fitur inti (misalnya autentikasi). Gunakan *mocking* API dari Postman untuk pengembangan awal. Sesuaikan tampilan jika kurang memuaskan. kalau tidak memberatkan bisa membuat *unit test* dan *integration test* untuk setiap fitur.

**Output:** `progress_frontend.md`, *unit test* dan fitur berjalan dengan baik

## 8. Validasi *Testplan Frontend*
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`, `testplan.md`

Periksa apakah semua fitur sudah berjalan sesuai *requirement* dan *testplan* (paling minimal). Kalau misal ada Lakukan berbagai jenis pengujian yang direncanakan (unit, integrasi, *end-to-end*, performa, *security*, UAT). Jika ada penyesuaian, lakukan *prompting* lagi atau kembali ke tahapan pengembangan fitur.

**Output:** `progress_frontend.md`, *frontend* siap digunakan

## Sisi *Backend*

## 5. Tentukan Konteks Proyek *Backend*
**Context:** `requirement.md`, `arsitektur.md`, `testplan.md`, `postman-collection.json`, `skema_database.plantuml`

Sama seperti *frontend*, tentukan struktur *folder*, paket (*package*) yang digunakan, *framework backend* (misalnya *Node.js/Express*, *Python/Django/Flask*, *Java/Spring*, *PHP/Laravel*), *database*, penamaan *file*, aturan *changelog*, urutan pengembangan fitur, dan aturan lainnya. Pertimbangkan aspek keamanan, performa, skalabilitas, dan *maintainability* aplikasi *backend*. Gunakan Git untuk *version control*, *project management tools* untuk manajemen tugas, dan lakukan *code review* secara berkala.

Buat berkas `context_backend.md` dengan informasi konteks proyek *backend*. Buat berkas `progress_backend.md` dengan informasi progres, kendala, dan solusi.

**TIPS:** Sama seperti *frontend*, mulai dari struktur dasar, kembangkan fitur satu per satu, langsung lakukan tes (termasuk *unit test*, *integration test*, dan *end-to-end test* jika memungkinkan), catat hasil tes dan *changelog*, **dan *push* kode ke GitHub**. **INGAT**, urutannya: fitur, tes, catat, *push*. Jika ada *error*, segera catat *error* tersebut. Kalau make Github Copilot. itu kita bisa nge masukin konteks nya dari link dokumentasi resmi. make #fetch terus masukin link nya. jadi bisa make versi yang ter update dari framework tersebut


**OUTPUT:** `context_backend.md`, `progress_backend.md`

## 6. Siapkan *Environment* Proyek *Backend*
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`

Instal dependensi, buat struktur *folder*, dan lakukan tes arsitektur. Jika menggunakan *framework* seperti Laravel atau Spring, *environment* biasanya sudah siap secara *default*.

**OUTPUT:** `progress_backend.md`, proyek siap digunakan, termasuk *unit test*

## 7. Siapkan *Database* & Model
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `skema_database.plantuml`

Berdasarkan skema *database* yang telah dibuat, implementasikan *database*-nya. Buat model dan *unit test*-nya. **UNIT TEST DI *BACKEND* WAJIB**.

**Output:** *Database* siap digunakan, `progress_backend.md`

## 8. Kembangkan Fitur Pertama hingga Fitur ke-N
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `skema_database.plantuml`

Kerjakan fitur satu per satu, mulai dari fitur inti (misalnya autentikasi). Buat *unit test* atau *integration test* untuk setiap fitur.

**Tips:** Mulai dari fitur inti terlebih dahulu, lakukan tes (termasuk *unit test* dan *integration test*), baru fitur lain, tes lagi. Terakhir *route*-nya, lalu tes *route*-nya.

**Output:** `progress_backend.md`, *unit test* dan fitur berjalan dengan baik

## 9. Cek *Testplan Backend*
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `testplan.md`

Periksa apakah semua fitur *backend* sudah berjalan sesuai *requirement* dan *testplan*. kalau ada  Lakukan berbagai jenis pengujian yang direncanakan (unit, integrasi,  *end-to-end*, performa, *security*). Jika ada penyesuaian, lakukan *prompting* lagi atau kembali ke tahapan pengembangan fitur.

**Output:** `testplan.md`, `progress_backend.md`, proyek *backend* siap digunakan

## 10. Cek Integrasi dan *Finishing*
**Context:** Proyek *frontend*, proyek *backend*, `context_frontend.md`, `context_backend.md`, `progress_frontend.md`, `progress_backend.md`, `postman-collection.json`, `testplan.md`

Lakukan pengujian integrasi antara *frontend* dan *backend*. Pastikan semua fitur terintegrasi dan berfungsi dengan baik secara keseluruhan. Lakukan juga *end-to-end test* dan *user acceptance testing* (UAT).

## 11. *Build* Aplikasi, *Deploy* (Keseluruhan)
**Context:** Proyek *backend*, `context_backend.md`, `progress_backend.md`, proyek *frontend*, `context_frontend.md`, `progress_frontend.md`

Atur *environment* ke *production* untuk *backend* dan *frontend*. Pilih platform *deployment* sesuai kebutuhan proyek (misalnya Vercel, Netlify, AWS, Heroku, DigitalOcean).

**Output:** Proyek *frontend* dan *backend* yang sudah di-*deploy*

## 12. *Maintenance* dan Peningkatan Berkelanjutan
**Context:** Proyek *frontend* dan *backend* yang sudah di-*deploy*

Setelah aplikasi di-*deploy*, tahap *maintenance* dan peningkatan berkelanjutan menjadi penting. Lakukan aktivitas berikut:

*   **Monitoring Aplikasi:** Pantau performa aplikasi, *uptime*, *error*, dan metrik lainnya. Gunakan *tools monitoring* seperti Prometheus, Grafana, New Relic, atau Datadog.
*   **Logging:** Implementasikan *logging* yang baik untuk mencatat aktivitas aplikasi dan memudahkan *debugging* jika terjadi masalah.
*   **Bug Fixing:** Perbaiki *bug* yang ditemukan oleh pengguna atau tim internal.
*   **Update dan Patch Keamanan:** Terapkan *update* dan *patch* keamanan secara berkala untuk menjaga keamanan aplikasi.
*   **Peningkatan Berkelanjutan:** Tambahkan fitur baru, optimalkan performa, dan tingkatkan kualitas aplikasi berdasarkan *feedback* pengguna dan analisis data.
*   **Evaluasi dan Peningkatan Model AI (Jika Relevan):** Jika aplikasi Anda menggunakan model AI, lakukan evaluasi performa model secara berkala. Lakukan *re-training*, *fine-tuning*, atau penggantian model jika diperlukan untuk meningkatkan akurasi dan efektivitas AI.

**Output:** Aplikasi yang terus berjalan dengan baik, aman, dan terus berkembang.

---

**Umpan Balik Inkonsistensi:**

Setelah meninjau dokumen yang telah Anda perbarui, berikut adalah beberapa potensi inkonsistensi atau area yang perlu diperhatikan:

1.  **Penomoran Tahapan Backend:** Seperti yang disebutkan sebelumnya, penomoran tahapan *Backend* dimulai dari 5 lagi, sama dengan *Frontend*. Ini masih berpotensi membingungkan. Meskipun pemisahan ini mungkin disengaja untuk memperjelas alur masing-masing sisi, secara keseluruhan, ini bukan penomoran yang berkelanjutan untuk seluruh proses pengembangan aplikasi. *Namun, jika tujuannya adalah untuk memisahkan alur Frontend dan Backend secara jelas, penomoran ini mungkin dapat diterima.*

2.  **Tahap 1.5 Pra-pemrosesan Data Hilang:** Tahap 1.5 mengenai Pra-pemrosesan Data yang sebelumnya ditambahkan hilang dari versi yang Anda berikan. Jika aplikasi Anda melibatkan AI yang memerlukan data, tahap ini mungkin penting untuk dipertimbangkan kembali dan dimasukkan di antara tahap 1 dan 2.

3.  **Ketidaksesuaian Judul Sub-bagian Frontend dan Backend:** Judul sub-bagian untuk *Frontend* adalah "Sisi *Frontend*", sementara untuk *Backend* hanya "Sisi *Backend*". Ada sedikit ketidak konsistenan dalam penggunaan tanda bintang (*). Sebaiknya diseragamkan, misal keduanya menggunakan tanda bintang: "Sisi *Frontend*" dan "Sisi *Backend*", atau keduanya tanpa tanda bintang: "Sisi Frontend" dan "Sisi Backend". *Namun, perbedaan ini sangat kecil dan mungkin bukan masalah besar.*

4.  **Penyebutan Unit Test di Frontend TIPS dan Tahap 7 vs. Validasi Testplan di Tahap 8:**
    *   Di bagian **TIPS Frontend Tahap 5**, disebutkan "langsung lakukan tes minimal unit testing".
    *   Di **Tahap 7 Frontend**, disebutkan "kalau bisa membuat *unit test* dan *integration test* untuk setiap fitur."
    *   Namun, di **Tahap 8**, judulnya adalah "Validasi *Testplan Frontend*", yang mengimplikasikan pengecekan *semua* jenis tes sesuai *testplan*, bukan hanya *unit test*.

    Ini mungkin sedikit tidak konsisten. Sebaiknya diperjelas tingkat pengujian yang diharapkan di setiap tahap. Apakah *unit test* adalah *minimal* di awal, dan kemudian di tahap validasi *testplan*, semua jenis pengujian sesuai *testplan* harus diperiksa?  Atau apakah ekspektasinya *unit test* dan *integration test* di tahap pengembangan fitur (Tahap 7), dan kemudian validasi *testplan* di tahap 8 adalah pengecekan *keseluruhan* sesuai *testplan* yang lebih luas?

5.  **Istilah "Validasi Testplan Frontend" di Tahap 8:** Judul "Validasi *Testplan Frontend*" mungkin kurang tepat. Kata "validasi" biasanya lebih terkait dengan memastikan *testplan* itu sendiri valid dan komprehensif di awal. Di tahap ini (Tahap 8), yang lebih tepat mungkin adalah **"Verifikasi *Testplan Frontend*"** atau **"Pengecekan *Testplan Frontend*"** atau **"Implementasi *Testplan Frontend*"** atau **"Pengujian *Frontend* Berdasarkan *Testplan*"**.  Intinya adalah tahap ini adalah tentang *melaksanakan* pengujian sesuai *testplan* dan memastikan *implementasi* sesuai *requirement*, bukan hanya *memvalidasi* *testplan*-nya.

**Saran Perbaikan Inkonsistensi (Opsional):**

*   **Penomoran Backend:** Pertimbangkan untuk melanjutkan penomoran *Backend* dari *Frontend* (misalnya, Frontend 1-9, Backend 10-18, dst.) jika ingin alur yang lebih linear, atau gunakan penomoran yang berbeda (misalnya, F1-F9, B1-B9) jika ingin penekanan pada pemisahan alur. *Saat ini, penomoran terpisah mungkin justru lebih mudah dibaca untuk alur Frontend dan Backend yang berbeda.*
*   **Tahap 1.5 Pra-pemrosesan Data:** Pertimbangkan untuk menambahkan kembali tahap ini jika relevan dengan aplikasi AI Anda.
*   **Judul Sub-bagian:** Seragamkan penggunaan tanda bintang pada judul sub-bagian *Frontend* dan *Backend*.
*   **Konsistensi Tingkat Pengujian:** Perjelas ekspektasi tingkat pengujian di setiap tahap, terutama di Tahap 5 TIPS, Tahap 7, dan Tahap 8 *Frontend*.  Mungkin bisa diubah menjadi:
    *   **Tahap 5 TIPS:** "...langsung lakukan tes, dimulai dengan *unit test*..."
    *   **Tahap 7:** "...kalau bisa buat *unit test* dan *integration test* untuk setiap fitur..."
    *   **Tahap 8:** **Verifikasi *Testplan Frontend***: "Lakukan pengujian *frontend* secara komprehensif sesuai *testplan*, termasuk *unit test*, *integration test*, *end-to-end test*, *performance test*, *security test*, dan UAT..."
*   **Judul Tahap 8 Frontend:** Ganti "Validasi *Testplan Frontend*" menjadi "Verifikasi *Testplan Frontend*" atau judul lain yang lebih sesuai dengan aktivitas pengujian dan implementasi *testplan*.

Secara keseluruhan, dokumen ini sudah cukup baik dan terstruktur. Inkonsistensi yang disebutkan di atas bersifat minor dan lebih ke arah peningkatan kejelasan dan konsistensi istilah.
