# Katta maqsadlar — sayt

Hamma ko'radi, faqat egasi (sizning Gmail) tahrirlaydi. Ma'lumotlar Supabase'da, sayt Vercel'da.

## Fayllar
- `index.html` — sayt (Halqalar, Gul, Idishlar, Kartalar ko'rinishlari, jurnal)
- `config.js` — Supabase manzili va ochiq kalit
- `supabase.sql` — jadval, ruxsatlar va hozirgi ma'lumotlar

## 1. Supabase
1. supabase.com → **New project** (nomi: `katta-maqsadlar`, mintaqa: Frankfurt yoki eng yaqini).
2. **SQL Editor** → `supabase.sql` ni to'liq joylang, `SIZNING_GMAIL@gmail.com` ni o'z Gmailingizga almashtiring → **Run**.
3. **Project Settings → API**: "Project URL" va "anon public" (yoki "Publishable") kalitni `config.js` ga yozing.
   `service_role` / `secret` kalitni hech qachon qo'ymang.
4. **Authentication → URL Configuration**: *Site URL* ga Vercel manzilingizni yozing (masalan `https://katta-maqsadlar.vercel.app`) va uni *Redirect URLs* ga ham qo'shing.

## 2. GitHub + Vercel
1. GitHub'da yangi repo: `katta-maqsadlar` → shu 3 faylni yuklang (`index.html`, `config.js`, `supabase.sql`).
2. vercel.com → **Add New → Project** → repo'ni tanlang → Framework: **Other** → **Deploy**.
3. Har safar GitHub'dagi fayl o'zgarsa, Vercel o'zi yangilaydi.

## 3. Kirish
- Saytning pastidagi **"Egasi sifatida kirish"** → Gmailingizni yozing → pochtaga kelgan havolani bosing.
- Kirgandan keyin **"Tahrirlash"** tugmasi chiqadi. O'zgartirib, **Saqlash** ni bosing.
- Birinchi kirgandan keyin: Supabase → Authentication → Sign In / Providers → **Allow new users to sign up** ni o'chirib qo'ying (begonalar ro'yxatdan o'tmasin; ular baribir tahrirlay olmaydi).

## Ixtiyoriy: "Google bilan kirish" tugmasi
Supabase → Authentication → Providers → **Google** ni yoqing (Google Cloud'dan OAuth Client ID/Secret kerak bo'ladi),
so'ng `config.js` da `GOOGLE_LOGIN: true` qiling.

## Keyin: o'z domeningiz
Vercel → Project → Settings → Domains → domeningizni qo'shing, so'ng Supabase'dagi Site URL'ni ham yangilang.
