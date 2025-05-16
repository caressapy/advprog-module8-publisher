# Publisher App

## Reflection

> **How many data will the publisher program send to the message broker in one run?**

Dalam satu kali eksekusi, program *publisher* akan mengirimkan **lima data** ke *message broker*. Hal ini bisa dilihat dari implementasi fungsi `main` di file `main.rs`, di mana fungsi `publish_event` dipanggil sebanyak lima kali dengan data yang berbeda. Setiap panggilan fungsi tersebut mewakili satu pesan atau *event* yang akan dikirimkan. Dengan demikian, secara total ada lima pesan yang akan dikirimkan selama program berjalan satu kali. Ini menunjukkan bahwa program telah dikonfigurasi untuk secara eksplisit mengirimkan lima data ke dalam sistem antrian (*message queue*).



> **The url of "amqp\://guest\:guest\@localhost:5672" is the same as the one in the subscriber program. What does it mean?**

Penggunaan URL `amqp://guest:guest@localhost:5672` pada program *publisher* yang sama dengan *subscriber* menunjukkan bahwa keduanya terhubung ke *message broker* yang sama. URL tersebut menunjuk ke broker RabbitMQ lokal yang berjalan di komputer (localhost) dengan kredensial default yaitu `guest` sebagai username dan password. Karena *publisher* dan *subscriber* berada di jalur koneksi yang sama, maka pesan yang dikirimkan oleh *publisher* akan bisa langsung diterima oleh *subscriber*. Jika mereka menggunakan URL yang berbeda, maka mereka bisa saja terhubung ke broker yang berbeda pula, sehingga proses pengiriman dan penerimaan pesan tidak akan berhasil. Kesamaan URL ini sangat penting untuk memastikan komunikasi antar program berjalan dengan lancar.


<img width="959" alt="image" src="https://github.com/user-attachments/assets/e768a6da-bb40-42e8-8a6e-d8cc801afa14" />
