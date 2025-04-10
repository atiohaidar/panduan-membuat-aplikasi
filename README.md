Tahapan buat aplikasi make AI
PENTING: Satu tahap bisa lebih dari satu kali prompting. Missal buat requriementent bisa jadi engga sekali prompt. Bahakan bisa 10 kali
Sentuhan manusia masih perlu BANGET. Apalagi klo masih banyak error
0.	Cari Ide Aplikasi
Output: ide aplikasi
1.	Tentuin Requirement
Context: ide aplikasi
Nanti buat requirement.md yang isina list fitur nya apa aja, aturannya gimana aja
Buat dalam user story nya juga. Tentuin juga flow dari aplikasinya kayak gimana
test plan juga dibuat. Test plan ini buat nanti setelah fitur nya beres di cek satu satu, firu ini udah belum, fitur itu udah belum dll
Output: requirement.md, testplan.md
2.	Tentuin Arsitektur umum aplikasi
Context: Markdown requirement
Misal frontend make apa, backend make apa, database make apa
Terus tentuin nanti berati buat apa aja. Alur data nya kayak gimana. Komunikasinya kaya gimana. 
Output: arsitektur.md
3.	Tentuin skema database
Context:requirement.md, arsitektur.md
Tentuin nanti database nya mau kayak gimana. Dari mana kemana dll
Skema datbasenya lengkap, dalam artian harus bener bener sampai kardinalitasnya
Output: skema_database.plantuml
4.	Tentuin API Documentation nya
Context: requirement.md, arsitektur.md, skema_database.plantuml
Buat api documentationnya untuk semua fitur yang ada
Nanti hasilnya  postman collection yang bisa dipake
Terus untuk fontend nya nanti buat dari mocking api dari postman. Dikasih example juga di postman nya 
https://www.youtube.com/watch?v=fWOf0iNRcbg

Ouput: postman-collection.json, mocking 
Sisi Frontend
5.	Tentuin Konteks project frontend
Context: requirement.md, arsitektur.md, plantest.md, postman-collection.json
Missal nanti struktur folder nyakayak gimana, package yang dipake apa aja , make frontend apa, missal boostrapt, terus style nya yang kayak gimana dll, penamaan file nya apa aja, aturan changelog nya kayak gimana.  Urutan fitur yang di buat apa aja, Aturanya apa aja. 
Terus di file progress_frontend isinya itu kayak list apa aja yang mau dikerjain. Checklist nya juga. Jadi keliatan apa yang udah dibuat dan apa yang belum dibuat. . terus di bawahnya juga ada evaluasi pengerjaan progressnya. Misalnya ada kendala apa aja,terus solusinya apa.  Kayak lesson learned nya. Jadi ada judul, terus deskripsi kendala nya apa, terus deskrispi solusinya apa. Solusinya bisa jadi belum dikerjakan atau masih error. Tergantung nanti bagaimana  kondisinya . pastiin struktur foldernya itu mudah di maintance. Jadi bisa gampang keliatan kalau mau ada perubahan A, berarti yang di ubah yang mana. Terus performansinya bagus
TIPS: aturan nya itu mulai buat dari struktur dasar nya dulu, terus buat fitur satu satu, habis itu langsung test. Setelah berhasil langsung dicommit, tambah changelog. INGET, urutannya fitur, test, catat, fitur, test, catat. Kalo ada error langsung catat error nya. Kasih status ini 
OUTPUT: context_frontend.md, progress_frontend.md
6.	Siapin environment project
Context: context_frontend.md, progress_frontend.md, postman-collection.json
Ini mulai install install project nya, dependensi nya, struktur folder nya. Terus buat test untuk arsitekturnya. Missal buat test routing, test nampilin frontend. Terus unit test sederhanya nya.  Apakah berhasil atau engga Kalo missal ada api, coba test make testing make cara routing kayak gitu bisa atau engga., pastiin evniroment nya aman kalo udah, lanjut


Unit test react: https://www.youtube.com/watch?v=i2MEVuInFKw
Note: engga selalu harus make unit test direact, tapi make yang ada aja 
OUTPUT: progress_frontend.md, project yang siap digunakan asik, unit test nya juga
7.	Buat fitur pertama sampai fitur ke N
Context: context_frontend.md, progress_frontend.md, postman-collection.json
Waktu projectnya siap di isi, buat per fitur, jangan langsung semuanya. Buat satu satu missal auth dulu.  terus test makemocking dari postman
Tampilannya di sesuain aja kalo kurang bagus
Ouput: progress_frontend.md, unit test dan fiturny aberjalan dengan baik

8.	Cek Testplan frontend nya
Context: context_frontend.md, progress_frontend.md, postman-collection.json, testplan.md
Cek apakah semua fitur udah berhasil dijalankan,. Iudah sesuai requirement bnelum. Kalo masih ada penyesuaian, prompting lagi
Output: progress_frontend.md, frontend nya sipa dipake

9.	Build Aplikasi, deploy
Context: project frontend, context_frontend.md, progress_frontend.md
Jangan lupa setting environment nya jadi production
Ini entah mau di mana bebsas, apa di vercel atau di mana gitu bebas, terugantung projectnya juga
Output project yang udah di deploy
Sisi Backend
5.	Tentuin Konteks project backend
Context: requirement.md, arsitektur.md, plantest.md, postman-collection.json, skema_database.plantuml
Missal nanti struktur folder nyakayak gimana, package yang dipake apa aja , make framework apa apa, missal database apa, penamaan file nya apa aja, aturan changelog nya kayak gimana.  Urutan fitur yang di buat apa aja, Aturanya apa aja. 
Terus di file progress_backend isinya itu kayak list apa aja yang mau dikerjain. Checklist nya juga. Jadi keliatan apa yang udah dibuat dan apa yang belum dibuat. . terus di bawahnya juga ada evaluasi pengerjaan progressnya. Misalnya ada kendala apa aja,terus solusinya apa.  Kayak lesson learned nya. Jadi ada judul, terus deskripsi kendala nya apa, terus deskrispi solusinya apa. Solusinya bisa jadi belum dikerjakan atau masih error. Tergantung nanti bagaimana  kondisinya . pastiin struktur foldernya itu mudah di maintance. Jadi bisa gampang keliatan kalau mau ada perubahan A, berarti yang di ubah yang mana
TIPS: aturan nya itu mulai buat dari struktur dasar nya dulu, terus buat fitur satu satu, habis itu langsung test. Setelah berhasil langsung dicommit, tambah changelog. INGET, urutannya fitur, test, catat, fitur, test, catat. Kalo ada error langsung catat error nya. Kasih status ini 
OUTPUT: context_backend.md, progress_backend.md
6.	Siapin environment project
Context: context_backend.md, progress_backend.md, postman-collection.json
Ini mulai install install project nya, dependensi nya, struktur folder nya. Terus buat test untuk arsitekturnya. Kalo make Laravel langsung jadi seharusnya, tinggal pake
OUTPUT: progress_backend.md, project yang siap digunakan asik, unit test nya juga
7.	Siapin database & model nya dulu
Context: context_backend.md, progress_backend.md, postman-collection.json, skema_database.plantuml
Darii data skema database yang udah dibuat, buatin juga implementasi database nya. Terus dari implementasi database, buat model nya. Habis itu jangan lupa buat unit testnya, UNIT TEST DI BACKEND ITU KUDU.
Output: database yang siap digunakan, progress_backend.md
8.	Buat fitur pertama sampai fitur ke N
Context: context_backend.md, progress_backend.md, postman-collection.json, skema_database.plantuml
Waktu projectnya siap di isi, buat per fitur, jangan langsung semuanya. Buat satu satu missal auth dulu.  terus buat unit test nya
Tips: buat nya dari yang ppaling intinya dulu, terus test, baru fitur tereus test, di akhirn baru route nya,terus test route nya 
Ouput:,progress_frontend.md, unit test dan fiturny aberjalan dengan baik

9.	Cek Testplan backend nya
Context: context_backend.md, progress_backend.md, postman-collection.json, testplan.md
Cek apakah semua fitur udah berhasil dijalankan,. udah sesuai requirement belum. Kalo masih ada penyesuaian, prompting lagi
Output: testplan.md, progress_backend.md, project backend nya siap dipake
Katakanla frontend dan baclkend jadi
10.	Cek integrasi dan finising
Context: project frontend, projectbackend, context frotned bacend.md, progress frotnedn backend..mdm postman-collection.json, testplan.md

11.	Build Aplikasi, deploy
Context: project backend, context_backend.md , progress_backend.md (yang frontend juga)
Jangan lupa setting environment nya jadi production
Ini entah mau di mana bebsas, apa di vercel atau di mana gitu bebas, terugantung projectnya juga
Output: project frontend dan backend yang udah di deploy

