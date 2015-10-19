#Panduan Singkat Upgrade Keuangan Guyub

Pada setiap rilis baru Keuangan Guyub, selalu disertakan informasi dan materi upgrade untuk 1 versi sebelumnya, jadi semisal rilis versi 2 maka akan disertakan informasi dan materi migrasi dari versi 1. Adapun langkah-langkah secara umum adalah;

**1. Walaupun upgrade Keuangan Guyub dirancang sedemikian rupa agar mudah dan aman bagi data sebelumnya, namun sangat dianjurkan untuk melakukan backup seluruh aplikasi yang telah ada, baik itu file aplikasi di web server maupun isi database.**

Untuk backup database Anda bisa menggunakan fitur Export di [PHPMyAdmin](http://www.phpmyadmin.net/), atau jika ingin menggunakan perintah di terminal/command line bisa menggunakan;

```
mysqldump -u root -p create kg > ../kg-old.sql
```

**2. Copy dan replace seluruh file aplikasi versi baru menggantikan aplikasi versi lama yang telah ada di webserver.**

**3. Eksekusi file query upgrade `(KG-Upgrade-(versi sebelumnya)-to-(versi sekarang].sql))`yang disertakan pada rilis baru yang terletak pada folder db (misal /kg/db/KG-Upgrade-1-to-2.sql).**

Anda bisa menggunakan fitur Import di [PHPMyAdmin](http://www.phpmyadmin.net/), atau jika ingin menggunakan perintah di terminal/command line bisa menggunakan;

```
mysql -u root -p kg < ../kg/db/KG-Upgrade-1-to-2.sql
```

**4. Setelah selesai langkah ke-3 seharusnya versi Keuangan Guyub Anda sudah ter-upgrade. Selanjutnya lakukan tes untuk memastikan keberhasilan upgrade.**


##  ##

Ket: Pada versi tertentu tidak tertutup kemungkinan ada langkah tambahan yang diperlukan untuk migrasi. Informasi tentang ini nantinya akan dituliskan juga di halaman ini secara khusus.