---
layout: post
title:  "Membuat Static Server Dengan Mudah Menggunakan Http-Server"
date:   2019-05-16 00:46:44 +0700
categories: jekyll update
---
Berawal dari kepengen nyetel lagu di laptop tapi sayangnya speaker laptop ternyata rusak sehingga suaranya gak kedengeran jelas, akhirnya gua kepikiran buat server biar file-file musik gua bisa disetel lewat perangkat lain. Sebenernya gua ada ``icecast`` yang biasa gua pakai buat bikin web streaming musik, tapi karna laptop gua kentang, RAM cuma 4 GB dan gua banyak jalanin aplikasi-aplikasi made by [electron](https://electronjs.org/ "electron") yang terkenal ngabisin memory, gua gak pakai itu.

Kepikiran juga buat pakai nginx, tapi repot juga musti konfigurasi lagi. Akhirnya googling deh sampe pada akhirnya ketemu tool ``http-server`` ini.

## Pengenalan

``http-server`` menurut gua adalah program paling simple yang digunakan untuk membuat server statis dengan konfigurasi yang gampang banget, bahkan bisa dibilang gak perlu konfigurasi lagi, sesuai yang ditulis oleh pembuatnya di halaman [npm http-server](https://www.npmjs.com/package/http-server "npm http-server").

> http-server is a simple, zero-configuration command-line http server. It is powerful enough for production usage, but it's simple and hackable enough to be used for testing, local development, and learning.

## Instalasi

Instalasi menggunakan package manager ``npm``:

``npm install http-server -g``

Tinggal tambah ``sudo`` ya kalo butuh akses root.

``sudo npm install http-server -g``

### Penggunaan

Cara penggunaannya gampang banget, sesuai yang ditulis di atas, gak perlu konfigurasi yang macam-macam, tinggal run http-server doang lewat terminal. Berikut langkah mudahnya :

1. Pindah ke directory yang mau dijadikan server menggunakan perintah ``cd``, contohnya disini kita mau jadikan directory Music kita sebagai server : ``cd Music``.

2. Setelah ada di directory yang kita mau tinggal deh run ``http-server``

3. Agar bisa diakses oleh perangkat di jaringan yang sama, kita buka dulu port yang dijalankan oleh ``http-server``. Secara default, port yang digunakan adalah port ``8080``. Untuk buka firewall portnya jalankan perintah ``sudo ufw allow 8080/tcp``. Buka firewallnya cukup sekali aja ya, jadi gak harus tiap jalanin ``http-server`` musti buka portnya lagi asalkan selama port ``http-server``-nya gak diganti.

4. Selesai, sekarang servernya sudah bisa diakses melalui localhost atau dari perangkat lain dengan mengakses http://ip-server-mu:8080 di browser.

## Options

Beberapa options yang sering digunakan, sisanya silahkan baca dokumentasinya di situs [http-server](https://www.npmjs.com/package/http-server "http-server") sendiri ya.

- ``-p`` merubah port
- ``-o`` membuka browser setelah ``http-server`` dijalankan.
- ``-r`` generate robots.txt. Pakai ini hanya kalo bisa diakses oleh internet/public.
- ``-h`` untuk bantuan.