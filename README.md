# Wazium WhatsApp Bot

![Logo](assets/images/wazium.png)

Wazium adalah WhatsApp Bot berbasis Node.js yang mudah dikembangkan, dengan fitur modular, auto-reload, dan siap digunakan untuk kebutuhan personal maupun komunitas.

## Fitur Utama
- Sistem perintah modular (mudah menambah/mengedit command)
- Hot-reload (perubahan file command & fungsi langsung aktif tanpa restart)
- Mendukung berbagai jenis pesan: teks, lokasi, kontak, polling, event, produk, tombol, list, kartu, dsb
- Logging perintah dengan tampilan tabel di konsol
- Konfigurasi global mudah diubah
- Dukungan pairing code login WhatsApp Web

## Instalasi
1. **Clone repository**
   ```bash
   git clone <repo-ini>
   cd wazium
   ```
2. **Install dependencies**
   ```bash
   npm install
   ```
3. **Konfigurasi**
   - Edit file `config.js` untuk mengubah nama bot, owner, dsb.
   - Siapkan file `.env` jika ingin menggunakan variabel lingkungan (misal: `BOTNUMBER`, `WEBHOOKS`).

4. **Jalankan Bot**
   ```bash
   npm start
   ```
   Atau langsung:
   ```bash
   node index.js
   ```

## Penggunaan
- Prefix default: `.` (titik)
- Contoh perintah:
  - `.help` — Menampilkan daftar perintah
  - `.text` — Balas "Hello World"
  - `.ping` — Cek response time bot
  - `.info` — Info chat & user

## Menambah/Mengedit Command
- Semua perintah di-handle di `commandHandler.js`.
- Tambahkan case baru pada switch-case di fungsi `handleCommand`.
- Contoh:
  ```js
  case 'halo':
    await WaziumBot.sendText(from, 'Halo juga!')
    break;
  ```

## Struktur Folder
- `index.js` — Entry point, auto-restart jika error
- `service/wazium.js` — Main logic WhatsApp bot
- `lib/` — Berisi fungsi, handler, loader, dsb
- `commandHandler.js` — Handler utama semua command
- `config.js` — Konfigurasi global bot
- `assets/images/` — Logo bot
- `session/` — Data session WhatsApp

## Konfigurasi Penting
Edit di `config.js`:
- `global.botname` — Nama bot
- `global.ownernumber` — Nomor owner (format internasional)
- `global.ownername` — Nama owner
- `global.xprefix` — Prefix command
- `global.thumb` — Path logo bot

## Kontribusi
Pull request & issue sangat diterima! Silakan fork, modifikasi, dan ajukan PR.

## Lisensi
MIT License

Copyright (c) 2025 lrnd.__

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

> Dibuat oleh [LRNDWY](https://github.com/lrndwyy) — Instagram: [@lrnd.__](https://instagram.com/lrnd.__)
