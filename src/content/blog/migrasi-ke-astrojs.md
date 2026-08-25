---
title: "Migrasi dari GatsbyJs ke AstroJS"
pubDate: 2026-08-26T00:25:54+02:00
lastmod: 2026-08-26T00:25:54+02:00
share:
  enable: true
  link: true
  twitter: true
  reddit: true
  bluesky: true
  hackernews: true

draft: false
license: "MIT"

tags: [astro, gatsbyjs, cloudflare]
categories: [Web]
description: "AstroJS membaut blog menjadi cepat karena meminimalkan Javascript"
---

Setelah beberapa hari memggunakan [GastbyJS](https://www.sudarblogger.com/blog/gatsbyjs/) akhir saya pindah lagi ke AstroJS sebagai piliham Platfrom blog saya saat ini, mungkin kalian berfikir nih orang kenapa gonta - ganti mulu ya? hehehe

Dari segi SEO aku akui kalau GatsbyJS ini saat cocok apalagi saat memindah blog banyak artikel dalam hitungan jam ke index oleh Google, bahkan hampir semua artikel saya sudah ke index semua oleh Google. 

> Lalu kenpaa pindah mas? bukannya sayang banget artikelnya sudah terindex lalu akan terjadi error di mesin pencari! 

Mungkin kalian berfikir seperti itu, karena melihat dari blog mas sugeng juga memindah blog nya jadi tidak ada salahnya untuk mencoba, kalaupun link nya nanti error mungkin hanya beberapa saja. 

## Apa sih AstroJS? 

Astro.js adalah sebuah web framework modern yang dirancang khusus untuk membangun situs web yang cepat dan berfokus pada konten dengan mengirimkan JavaScript minimal ke browser.

Apabila menggunakan AstroJS ini tentu akan meminimalkan penggunaan Javascript dan akan membuat blog menjadi kecang saat di akses. 

Alsan mengapa saya memilih AstoJS ini :
- **Arsitektur Pulau** (Islands Architecture): Astro merender sebagian besar halaman menjadi HTML statis yang ringan. Bagian halaman yang butuh interaksi (seperti tombol interaktif atau kolom komentar) dipisahkan menjadi "pulau" kecil yang hanya memuat JavaScript saat benar-benar diperlukan.
- **Bebas Memilih Framework UI** (Bring Your Own Framework): Anda tetap bisa menggunakan komponen dari library populer seperti React, Vue, Svelte, atau Solid.js di dalam proyek Astro Anda.
- **Performa Tinggi Secara Bawaan** (Zero JavaScript by Default): Tanpa konfigurasi tambahan, Astro menghapus semua kode JavaScript yang tidak diperlukan di sisi klien sehingga halaman termuat dengan sangat cepat dan ramah SEO.

## Hosting di Clouflare Pages
Sebenarnya ada banyak pilihan hlating yang populer seperti Vercel, Akan tetapi saya tetap milih Cloudflare sebagai hosting blog saya ini, Ada beberapa alasan mengapa saya tetap milih Cloudflare : 

- **Biaya Lebih Rendah**: Paket gratis Cloudflare Pages sudah sangat memadai untuk kebutuhan saya.
- **Integrasi DNS & Proxy**: Integrasi lancar dengan layanan DNS dan proxy Cloudflare yang sudah saya gunakan.
- **Cloudflare Rules**: Memudahkan pengaturan redirect dan transformasi.
- **Point of Presence (POP) di Indonesia**: Kehadiran server Cloudflare di Indonesia menjamin kecepatan loading yang lebih baik untuk pengunjung lokal.
- **Kompatibilitas**: Vercel dan Netlify tidak merekomendasikan penggunaan proxy Cloudflare, sementara saya ingin tetap menggunakan layanan Cloudflare lainnya.
- **Uptime yang Andal**: Tidak perlu diragukan lagi, uptime Cloudflare sangat bisa diandalkan, memberikan keamanan bahwa website akan selalu tersedia bagi pengunjung.

## AstroJS vs GatsbyJS
Agar tidak salah pilih CMS maka disini mari kita badingkan Astrojs dengan GatsbyJs ini :

**​Keunggulan Astro.js:**

- Multi-Framework: Bebas menggunakan komponen dari React, Svelte, atau Vue dalam satu proyek secara bersamaan.
- Kurva Belajar Rendah: Menggunakan sintaks mirip HTML (.astro) yang intuitif dan mudah dipahami.
- Optimasi Konten: Sangat efisien untuk situs berbasis teks seperti blog, dokumentasi, dan portofolio.
- ​Islands Architecture: Mengirimkan HTML murni ke browser dan hanya mengunduh JavaScript pada komponen interaktif tertentu.

**​Keunggulan Gatsby.js:**
​
- Ekosistem React yang Luas: Memanfaatkan penuh pustaka, alur kerja, dan tooling dari ekosistem React.
- ​Ekosistem Plugin Melimpah: Menyediakan ribuan plugin siap pakai untuk integrasi CMS, SEO, dan manipulasi gambar.
- GraphQL Terintegrasi: Memudahkan pengelolaan dan penggabungan data dari berbagai headless CMS secara terstruktur.
- Rendering Hibrida: Mendukung Deferred Static Generation (DSG) dan SSR untuk menangani ribuan halaman dinamis.


## Theme Apa Yang di Pakai? 

Tentu yang berkunjung di blog ini pada bertanya template apa yang saya pakai, disini saya menggunakan template karya devoloper Vuk1lis, dimana theme nya sesuai yang saya harapkan ditambah tidak terlalu wah juga, karena ini blog nya bersifat personal jadi tidak perlu lah memiliki banyak fitur yang wah cukup sewajar nya aja. 

