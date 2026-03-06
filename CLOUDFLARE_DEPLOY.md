# Deploy ke Cloudflare Pages (Free)

## Ringkasan
- Project ini sudah static (`index.html`, `css/`, `js/`, `img/`), jadi bisa langsung deploy ke Cloudflare Pages tanpa server.
- Fitur komentar/rating menggunakan `localStorage` browser, bukan database.

## Langkah Deploy
1. Push project ke GitHub repository.
2. Login ke Cloudflare Dashboard.
3. Buka `Workers & Pages` -> `Create` -> `Pages` -> `Connect to Git`.
4. Pilih repository ini.
5. Build settings:
   - Framework preset: `None`
   - Build command: (kosongkan)
   - Build output directory: `/` (root)
6. Klik `Save and Deploy`.

## Pointing Domain
1. Di project Pages, buka tab `Custom domains`.
2. Klik `Set up a custom domain`.
3. Masukkan domain Anda, contoh: `yushitart.com`.
4. Ikuti instruksi DNS Cloudflare (umumnya CNAME/flattening otomatis jika nameserver sudah di Cloudflare).

## Catatan Penting
- Data komentar tersimpan per browser/per device pengunjung, tidak sinkron antar pengguna.
- Jika butuh komentar global yang sama untuk semua pengunjung tanpa database tradisional, opsi berikut cocok:
  - Cloudflare Worker + KV
  - Atau integrasi layanan komentar pihak ketiga.
