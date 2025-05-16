# Publisher App

## Reflection

> **How many data will the publisher program send to the message broker in one run?**

Program *publisher* akan mengirim **lima data** ke *message broker* dalam satu kali eksekusi. Hal ini terlihat dari pemanggilan fungsi `publish_event` sebanyak lima kali di dalam fungsi `main` pada file `main.rs`.

> **The url of "amqp\://guest\:guest\@localhost:5672" is the same as the one in the subscriber program. What does it mean?**

Alamat URL `amqp://guest:guest@localhost:5672` yang digunakan di program *publisher* sama persis dengan yang digunakan di *subscriber*. Artinya, kedua program terhubung ke *message broker* yang sama. Dengan begitu, setiap *message* yang dikirim oleh *publisher* dapat diterima oleh *subscriber*. Jika URL-nya berbeda, maka *publisher* dan *subscriber* akan berada di sesi atau broker yang berbeda, sehingga *subscriber* tidak akan bisa menerima pesan dari *publisher* tersebut.
