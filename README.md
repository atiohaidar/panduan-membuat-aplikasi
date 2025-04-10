
# Langkah-Langkah Pengembangan Aplikasi Berbasis AI

**PENTING:**

*   Setiap tahapan dapat melibatkan beberapa kali *prompting*. Misalnya, pembuatan *requirement* bisa memerlukan lebih dari satu *prompt*, bahkan mungkin hingga 10 kali.
*   Sentuhan manusia tetap sangat penting, terutama saat masih banyak *error*.
*   Pertimbangkan aspek non-fungsional seperti keamanan, performa, skalabilitas, *accessibility*, dan *maintainability* di setiap tahapan yang relevan.
*   Jika bekerja dalam tim, kolaborasi tim sangatlah penting. Gunakan alat kolaborasi seperti Git untuk *version control*, *project management tools*, dan lakukan *code review* secara berkala.

**Tips Penggunaan *Prompting*:** *Prompting* dapat dimanfaatkan di berbagai tahapan untuk membantu mempercepat dan meningkatkan kualitas pengembangan. 

*   *Brainstorming* ide aplikasi.
*   Menghasilkan daftar fitur awal dan *user story*.
*   Merumuskan draf arsitektur, skema *database*, dan dokumentasi API.
*   Membuat *template code*, *mockup* UI, dan *unit test* awal.
*   Mendapatkan saran solusi untuk kendala teknis.

**Setiap kali ada pembaruan fitur, jangan lupa untuk *push* kode ke GitHub.**

## 0. Cari Ide Aplikasi
**Output:** Ide aplikasi

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk *brainstorming* ide aplikasi berdasarkan topik atau masalah tertentu. Misalnya, "*Berikan 10 ide aplikasi AI yang bermanfaat untuk pendidikan.*"

## 1. Tentukan *Requirement*
**Context:** Ide aplikasi

Buat berkas `requirement.md` yang berisi daftar fitur dan aturan aplikasi. Susun juga dalam bentuk *user story* dan tentukan alur aplikasi. Buat juga `testplan.md` yang lebih komprehensif, mencakup berbagai jenis pengujian setidaknya untuk apa yang user butuhkan. tapi lebih baik lagi jika ingin detail seperti *unit test*. Paling minimal: *integration test*, *end-to-end test*, *performance test*, *security test*, dan *user acceptance testing* (UAT) (*automated testing*) jika memungkinkan.

**Output:** `requirement.md`, `testplan.md`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan daftar fitur awal berdasarkan ide aplikasi, atau untuk merumuskan *user story*. Misalnya, "*Berdasarkan ide aplikasi 'Aplikasi Pembelajaran Bahasa AI', buat daftar fitur utama dan user story untuk fitur 'Kamus Interaktif'.*"


## 2. Tentukan Arsitektur Umum Aplikasi
**Context:** Berkas `requirement.md`,`testplan.md` 

Tentukan teknologi yang digunakan untuk *frontend*, *backend*, dan *database*. Rancang alur data dan komunikasi antar komponen. Pertimbangkan aspek keamanan dan skalabilitas dalam arsitektur aplikasi.

**Output:** `arsitektur.md`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk menghasilkan saran arsitektur berdasarkan *requirement* aplikasi. Misalnya, "*Berdasarkan requirement aplikasi e-commerce, sarankan arsitektur umum yang scalable dan aman.*"

## 3. Tentukan Skema *Database*
**Context:** `requirement.md`, `arsitektur.md`

Rancang skema *database* secara lengkap menggunakan plantuml, termasuk hubungan antar tabel dan entitas hingga kardinalitasnya.

**Output:** `skema_database.plantuml`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu membuat draf awal skema *database* berdasarkan *requirement* fitur dan entitas data yang diidentifikasi. Misalnya, "*Berdasarkan fitur 'manajemen pengguna', 'produk', dan 'keranjang belanja' untuk aplikasi e-commerce, buat draf skema database relasional.*"

## 4. Tentukan API Documentation
**Context:** `requirement.md`, `arsitektur.md`, `skema_database.plantuml`, testplan.md

Buat dokumentasi API untuk semua fitur yang ada. Hasilnya berupa *Postman Collection* yang dapat digunakan, termasuk *mocking* API dari Postman dengan contoh *request* dan *response*.

[Referensi Mocking API Postman](https://www.youtube.com/watch?v=fWOf0iNRcbg)

**Output:** `postman-collection.json`, *mocking* API

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan draf awal dokumentasi API berdasarkan fitur-fitur yang didefinisikan dalam *requirement*. Misalnya, "*Buat draf dokumentasi API untuk endpoint 'GET /products' yang mengembalikan daftar produk, dengan contoh request dan response dalam format JSON.*"

## Sisi *Frontend*

## 5. Tentukan Konteks Proyek *Frontend*
**Context:** `requirement.md`, `arsitektur.md`, `testplan.md`, `postman-collection.json`

Tentukan struktur *folder* proyek, paket (*package*) yang digunakan, teknologi *frontend* (misalnya *React*, *Vue*, *Angular*, *Bootstrap*, *Tailwind CSS*), gaya (*style*), penamaan *file*, aturan *changelog*, urutan pengembangan fitur, dan aturan lainnya. Pertimbangkan aspek performa, *accessibility*, dan *maintainability* aplikasi *frontend*. Gunakan Git untuk *version control*, *project management tools* untuk manajemen tugas, dan lakukan *code review* secara berkala.

Buat berkas `context_frontend.md` yang mendokumentasikan semua keputusan ini. Buat juga berkas `progress_frontend.md` yang berisi daftar tugas yang akan dikerjakan dan *checklist* progres. Di bagian bawah `progress_frontend.md`, tambahkan evaluasi progres pengerjaan, kendala, dan solusi (mirip *lesson learned*). Setiap kendala dan solusi didokumentasikan dengan judul dan deskripsi. Pastikan struktur *folder* mudah di-*maintain* dan *performance* aplikasi baik.

**TIPS:** Mulai dari struktur dasar, kembangkan fitur satu per satu, langsung lakukan tes minimal unit testing,  dan *update progress*, **dan *push* kode ke GitHub**. **INGAT**, urutannya: fitur, tes, catat, *push*. Jika ada *error*, segera catat *error* tersebut.

**OUTPUT:** `context_frontend.md`, `progress_frontend.md`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan struktur *folder* proyek awal, daftar *package* yang umum digunakan untuk teknologi *frontend* tertentu, atau contoh konfigurasi *linting* dan *formatting*. Misalnya, "*Buat contoh struktur folder proyek React yang umum digunakan dan mudah di-maintain.*"

## 6. Siapkan *Environment* Proyek *Frontend*
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`

Instal dependensi proyek, buat struktur *folder*, dan buat tes arsitektur (misalnya tes *routing* dan tampilan *frontend*). Lakukan *unit test* sederhana. Pastikan *environment* aman sebelum melanjutkan.

[Referensi Unit Test React](https://www.youtube.com/watch?v=i2MEVuInFKw)

**Catatan:** *Unit test* tidak harus selalu menggunakan React, sesuaikan dengan teknologi yang digunakan.

**OUTPUT:** `progress_frontend.md`, proyek siap digunakan, termasuk *unit test*

## 7. Kembangkan Fitur Pertama hingga Fitur ke-N
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`

Setelah proyek siap, kerjakan fitur satu per satu, jangan langsung semuanya. Mulai dengan fitur inti (misalnya autentikasi). Gunakan *mocking* API dari Postman untuk pengembangan awal. Sesuaikan tampilan jika kurang memuaskan. kalau bisa  membuat *unit test* dan *integration test* untuk setiap fitur.

**Output:** `progress_frontend.md`, *unit test* dan fitur berjalan dengan baik

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan *template code* awal untuk fitur tertentu, atau untuk membuat *mockup* UI sederhana berdasarkan deskripsi fitur. Misalnya, "*Buat contoh kode React untuk form login sederhana dengan validasi input dasar.*"

## 8. Validasi *Testplan Frontend*
**Context:** `context_frontend.md`, `progress_frontend.md`, `postman-collection.json`, `testplan.md`

Periksa apakah semua fitur sudah berjalan sesuai *requirement* dan *testplan*. Kalau ada Lakukan berbagai jenis pengujian yang direncanakan (unit, integrasi, *end-to-end*, performa, *security*, UAT). Jika ada penyesuaian, lakukan *prompting* lagi atau kembali ke tahapan pengembangan fitur.

**Output:** `progress_frontend.md`, *frontend* siap digunakan

## Sisi *Backend*

## 5. Tentukan Konteks Proyek *Backend*
**Context:** `requirement.md`, `arsitektur.md`, `testplan.md`, `postman-collection.json`, `skema_database.plantuml`

Sama seperti *frontend*, tentukan struktur *folder*, paket (*package*) yang digunakan, *framework backend* (misalnya *Node.js/Express*, *Python/Django/Flask*, *Java/Spring*, *PHP/Laravel*), *database*, penamaan *file*, aturan *changelog*, urutan pengembangan fitur, dan aturan lainnya. Pertimbangkan aspek keamanan, performa, skalabilitas, dan *maintainability* aplikasi *backend*. Gunakan Git untuk *version control*, *project management tools* untuk manajemen tugas, dan lakukan *code review* secara berkala.

Buat berkas `context_backend.md` dengan informasi konteks proyek *backend*. Buat berkas `progress_backend.md` dengan informasi progres, kendala, dan solusi.

**TIPS:** Sama seperti *frontend*, mulai dari struktur dasar, kembangkan fitur satu per satu, langsung lakukan tes (termasuk *unit test*, *integration test*, dan *end-to-end test* jika memungkinkan), catat hasil tes dan *changelog*, **dan *push* kode ke GitHub**. **INGAT**, urutannya: fitur, tes, catat, *push*. Jika ada *error*, segera catat *error* tersebut.

**OUTPUT:** `context_backend.md`, `progress_backend.md`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan struktur *folder* proyek *backend* awal, daftar *package* yang umum digunakan untuk *framework backend* tertentu, atau contoh konfigurasi *routing* dan *middleware*. Misalnya, "*Buat contoh struktur folder proyek Node.js Express yang umum digunakan untuk REST API.*"

## 6. Siapkan *Environment* Proyek *Backend*
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`

Instal dependensi, buat struktur *folder*, dan lakukan tes arsitektur. Jika menggunakan *framework* seperti Laravel atau Spring, *environment* biasanya sudah siap secara *default*.

**OUTPUT:** `progress_backend.md`, proyek siap digunakan, termasuk *unit test*

## 7. Siapkan *Database* & Model
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `skema_database.plantuml`

Berdasarkan skema *database* yang telah dibuat, implementasikan *database*-nya. Buat model dan *unit test*-nya. **UNIT TEST DI *BACKEND* WAJIB**.

**Output:** *Database* siap digunakan, `progress_backend.md`

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan kode model (*ORM*) awal berdasarkan skema *database*. Misalnya, "*Berdasarkan skema database untuk tabel 'products', buat contoh kode model Sequelize (Node.js) yang sesuai.*"

## 8. Kembangkan Fitur Pertama hingga Fitur ke-N
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `skema_database.plantuml`

Kerjakan fitur satu per satu, mulai dari fitur inti (misalnya autentikasi). Buat *unit test* atau *integration test* untuk setiap fitur.

**Tips:** Mulai dari fitur inti terlebih dahulu, lakukan tes (termasuk *unit test* dan *integration test*), baru fitur lain, tes lagi. Terakhir *route*-nya, lalu tes *route*-nya.

**Output:** `progress_backend.md`, *unit test* dan fitur berjalan dengan baik

*Contoh Penggunaan Prompting:* Gunakan *prompting* untuk membantu menghasilkan *template code* awal untuk *controller*, *service*, atau *repository* berdasarkan deskripsi fitur. Misalnya, "*Buat contoh kode controller Node.js Express untuk endpoint 'POST /products' yang membuat produk baru, termasuk validasi input dan penanganan error.*"

## 9. Cek *Testplan Backend*
**Context:** `context_backend.md`, `progress_backend.md`, `postman-collection.json`, `testplan.md`

Periksa apakah semua fitur *backend* sudah berjalan sesuai *requirement* dan *testplan*. kalau ada  Lakukan berbagai jenis pengujian yang direncanakan (unit, integrasi,  *end-to-end*, performa, *security*). Jika ada penyesuaian, lakukan *prompting* lagi atau kembali ke tahapan pengembangan fitur.

**Output:** `testplan.md`, `progress_backend.md`, proyek *backend* siap digunakan

## 10. Cek Integrasi dan *Finishing*
**Context:** Proyek *frontend*, proyek *backend*, `context_frontend.md`, `context_backend.md`, `progress_frontend.md`, `progress_backend.md`, `postman-collection.json`, `testplan.md`

Lakukan pengujian integrasi antara *frontend* dan *backend*. Pastikan semua fitur terintegrasi dan berfungsi dengan baik secara keseluruhan. Lakukan juga *end-to-end test* dan *user acceptance testing* (UAT).

## 11. *Build* Aplikasi, *Deploy* (Keseluruhan)
**Context:** Proyek *backend*, `context_backend.md`, `progress_backend.md`, proyek *frontend`, `context_frontend.md`, `progress_frontend.md`

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

Semoga versi yang diperbarui ini lebih sesuai dengan harapan Anda dan memberikan panduan yang lebih lengkap dan bermanfaat!
