# Rapz Digital Store — Netlify / LocalStorage

## Deploy
1. Upload ZIP ini ke Netlify atau hubungkan repository Git.
2. Build command kosong.
3. Publish directory: `public`
4. Functions directory: `netlify/functions`
5. Buka website.

## Login admin default
- Email: `rapzadmin@gmail.com`
- Password: `rply7788`

**Penting:** kredensial tersebut adalah kredensial demo yang diminta. Jangan gunakan password ini untuk produksi.

## Database
Aplikasi menyimpan database runtime di `localStorage` browser dengan key:
`rapz_store_db_v1`

`public/assets/seed-database.json` hanya seed/dokumentasi. Browser tidak bisa menulis balik `database.json` di server Netlify.

## BayarLink
Admin memasukkan URL BayarLink pada produk berbayar. Setelah pembayaran, kode akses harus diberikan melalui sistem pembayaran/admin. Website kemudian memvalidasi kode terhadap kode produk.

## Upload gambar
Versi ini memakai URL gambar. Untuk galeri/file upload permanen lintas pengguna, diperlukan storage/backend seperti object storage.

## Batasan penting
Karena hanya LocalStorage + static Netlify:
- data user, pembelian, komentar, rating, chat dan perubahan admin hanya tersimpan pada browser/device tersebut;
- admin di HP/laptop lain tidak otomatis melihat perubahan dari browser pertama;
- file database.json tidak menjadi database server;
- password sudah di-hash SHA-256 di browser, tetapi autentikasi client-only tidak cocok untuk produksi.

Untuk toko sungguhan multi-user, gunakan database/server-side auth dan storage.
