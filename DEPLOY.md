# Deploy Gratis: Vercel + Supabase

## 1. Buat project Supabase
- Login ke [Supabase](https://supabase.com/)
- Buat project baru
- Buka `SQL Editor`
- Jalankan isi file `SETUP.sql`

## 2. Siapkan environment variable
Buat file `.env.local` dari `.env.example`:

```bash
cp .env.example .env.local
```

Lalu isi:
- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_ANON_KEY`

## 3. Jalankan lokal
```bash
npm install
npm run dev
```

## 4. Deploy ke Vercel
- Push project ke GitHub
- Import repo ke Vercel
- Framework preset: `Vite`
- Build command: `npm run build`
- Output directory: `dist`
- Tambahkan environment variables yang sama seperti `.env.local`
- Klik `Deploy`

## 5. Catatan gratis dan aman
- Frontend statis ini cocok untuk Vercel Hobby
- Database, Auth, dan Storage bisa pakai Supabase Free untuk MVP
- Fitur AI dan WhatsApp memakai token di browser. Untuk production publik, pindahkan token tersebut ke serverless function sebelum dipakai luas.
- Setelah update `SETUP.sql`, jalankan ulang policy SQL supaya aturan storage terbaru aktif.

## 6. Urutan rekomendasi sebelum go-live
1. Jalankan ulang `SETUP.sql`
2. Isi env Supabase
3. Test login, upload foto, dan CRUD data
4. Deploy ke Vercel
5. Baru aktifkan fitur AI/WA jika memang diperlukan
