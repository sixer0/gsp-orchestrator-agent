Temuan Issue dari workflow orkestrasi :
1. request-translator :
   - Masih menulis 02.structured, ini adalah artifact yang harusnya dikelola oleh task architect. saat request translator memberikan informasi untuk di berikan kepada task-architect sebaiknya dituliskan sebagai note di 01.translated saja (tidak perlu membuat 02.structured, agar workflow tidak terganggu)
   - Masih gagal mendapatkan intent untuk output .md / dokumen lain, padahal user sudah statement di original requestnya
2. task-architect :
   - Melakukan batching pada rencana orkestrasi yang potensial menyebabkan halusinasi / miss dependency. seharusnya setiap task dijalankan secara terpisah dengan dependency yang jelas.
   - Tidak mengelola state dan context antar task, sehingga task selanjutnya tidak memiliki akses ke output atau metadata dari task sebelumnya.
   - Output structured tidak konsisten dan tidak controller/orchestrator friendly (masih naratif yang bisa ambigu)
   - Perlu ada ringkasan rekomendasi / next plan di akhir task berdasarkan dari semua temuan / progress. disampaikan ke human in loop. dan harus didelegasikan ke master-controller untuk mencatat dalam artifact khusus rekomendasi.
3. master-controller :
   - Miss human in loop gate (biasanya ditrigger ketika 02.structured sudah siap)
   - tidak memvalidasi output 02.structured sudah controller/orchestration friendly. harusnya jika ada ambigu atau format rencana orchestrasi yang kurang baik di delegasikan ulang ke task-architect sebelum melanjutkan ke human in loop
   - setelah report task complete tidak menyimpan informasi di global / project memory

Sumber temuan issue : Riset R1-R3 GSP Arsenal
