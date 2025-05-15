# Reflection Tutorial Modul 9

**Zufar Romli Amri**  
**NPM**: 2306202694  
**Kelas**: A

---

### a. What is amqp?

**Jawab:**

AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi standar terbuka yang dirancang untuk pertukaran pesan antar aplikasi atau komponen sistem secara andal. Protokol ini berfungsi sebagai middleware untuk komunikasi asinkron dan memungkinkan aplikasi yang berbeda untuk saling bertukar informasi tanpa harus terhubung secara langsung. AMQP mendukung berbagai pola komunikasi seperti publish/subscribe, point-to-point, routing berbasis topik, dan mendukung fitur seperti transaksi, konfirmasi pengiriman, dan mekanisme antrian yang kokoh. Implementasi populer dari AMQP termasuk RabbitMQ, ActiveMQ, dan Apache Qpid, yang memungkinkan sistem terdistribusi untuk berkomunikasi secara efisien bahkan ketika aplikasi-aplikasi tersebut ditulis dalam bahasa pemrograman yang berbeda atau berjalan pada platform yang berbeda.

---

### b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for? 

**Jawab:**

String koneksi "amqp://guest:guest@localhost:5672" adalah URI (Uniform Resource Identifier) yang digunakan untuk menghubungkan ke server AMQP dengan komponen yang dapat diuraikan sebagai berikut: "guest" pertama adalah username untuk autentikasi ke server AMQP, yang dalam hal ini menggunakan kredensial default yang biasanya disediakan oleh implementasi server AMQP seperti RabbitMQ. "guest" kedua adalah password yang sesuai dengan username tersebut, juga merupakan nilai default. Sementara "localhost:5672" menunjukkan alamat server AMQP di mana "localhost" adalah nama host yang merujuk ke komputer lokal tempat aplikasi berjalan, dan "5672" adalah nomor port standar yang digunakan oleh protokol AMQP. Dengan string koneksi ini, aplikasi dapat melakukan autentikasi dan membuat saluran komunikasi dengan broker pesan AMQP yang berjalan pada mesin lokal melalui port tersebut, memungkinkan aplikasi untuk mengirim dan menerima pesan sesuai dengan konfigurasi yang ditetapkan dalam kode.

---

## Simulation slow subscriber

![/simulation-slow-subscriber](./images/simulation-slow-subscriber.jpg)

Jumlah antrean (queue) yang terlihat sebagai 2 pada tampilan RabbitMQ tersebut disebabkan karena dalam sistem terdapat dua antrean yang telah dibuat dan masih aktif. Hal ini bisa terjadi, misalnya, jika pada saat pengujian atau simulasi dilakukan pembuatan dua antrean berbeda—baik secara eksplisit oleh aplikasi publisher atau karena subscriber terhubung ke antrean berbeda. Jumlah ini tidak menunjukkan jumlah pesan, melainkan jumlah antrean yang ada di dalam broker RabbitMQ saat ini, terlepas dari apakah antrean tersebut sedang kosong atau terisi.