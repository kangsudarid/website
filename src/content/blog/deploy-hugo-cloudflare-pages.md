---
title: "Deploy Hugo to Cloudflare Pages"
pubDate: 2026-01-30T21:27:55+02:00
lastmod: 2026-01-30T21:27:55+02:00
share:
  enable: true
  link: true
  twitter: true
  reddit: true
  bluesky: true
  hackernews: true

draft: false
license: "MIT"

tags: [astro, hugo, adsense]
categories: [Web]
description: "Cara Hosting Hugo di Cloudflate Pages 2026"
---

Hugo adalah CMS Blog yang populer dikalangan devoloper, saya saat pindah ke Static Site Generator juga menggunakan Hugo ini, bahkan Mas Sugeng pun memakai Hugo untuk blog nya. 

Ada yang sudah tau mengenai Hugo ini? Jika belum tau atau belum akan jelaskan sedikit mengenai Hugo ini. 

## Apa Itu Hugo? 

Hugo adalah generator situs statis (static site generator) sumber terbuka yang ditulis dalam bahasa pemrograman Go (Golang). Alat ini mengubah berkas konten Markdown dan template menjadi halaman web HTML statis yang sangat cepat, aman, dan tidak memerlukan basis data (database). 

## Deploy Hugo di Cloudflare Pages

Karena disini saya memakai Handphone untuk deploy Hugo jadi sebelum nya sudah memiliki theme hugo ini dahulu, theme hugo yang pernah saya pakai ini merupakaan theme karya ardiantara. Karena ada beberapa alasan maka dari itu pindah atau migrasi blog, sebenarnya CMS banyak sekali untuk ngeblog ada AstroJS, NextJS, GatsbyJS dan masih banyak lagi. 

- Masuk ke Cloudflare
- Pilih Workers and Pages
- Connect Akun Git Milik Kalian
- Setelah Connect Pilih Repository yang sudah di simpan tadi
- Pilih Hugo untuk Build nya hugo --minify
- Build Directory nya pilih aja Public
- Klik Save and Deploy

Tunggu beberapa menit hingga proses selesai biasanya membutuhkan waktu 5 menitan untuk deplay nya. 

Apabila sudah selesai pilih aja Continue Project. 

