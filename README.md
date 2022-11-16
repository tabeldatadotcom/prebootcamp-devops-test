# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Jawaban 

1. DevOps adalah sebuah culture untuk mengkoordinasikan antar tim, yaitu tim Development dengan tim Operations dengan efektif dan efisien.
2. Infrastructure merupakan kumpulan komponen yang ditentukan oleh software dalam membentuk linkungan IT perusahaan.
3. Server adalah pengelola sumber daya, karena sebuah server dapat melakukan penyimpanan, pengiriman, dan penerimaan data.
    - Web Server : Apache
    - Database Server : MySQL Databse, PosgreSQL
4. Karena server menyediakan layanan penting yang dibutuhkan untuk pengembangan suatu software, antara lain : penyedia resource, pusat data dan backup data
5. Virtualisasi dan Container :
    - Virtualisasi : membagi resource hardware dari satu hardware fisik menjadi beberapa sistem komputer.
    - Container : virtualisasi tingkat sistem operasi, karena hanya menyediakan kebutuhan minimum yang dibutuhkan sebuah aplikasi agar bisa berjalan.
6. Teknologi Container begitu populer saat ini karena dapat memudahkan dalam mengembangkan suatu proyek, dengan adanya teknologi container ini kita tidak perlu repot melakukan konfigurasi, kita bisa melakukan deploy dengan teknologi container.
7. Orchestration Container System adalah proses untuk mengelola penyebaran, integrasi, penskalaan, dan siklus hidup perangkat lunak dan aplikasi dalam container di lingkungan yang kompleks dan dinamis. Sebagai alat otomatisasi, Orchestration Container menganalisis, mengatur, dan mengintegrasikan aplikasi dan layanan di tingkat operasi dasar.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

