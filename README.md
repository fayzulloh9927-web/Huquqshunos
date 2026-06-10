# Huquqshunos — Netlify'ga deploy qilish

Bu **statik, yagona fa!l** (`index.html`) — build, server yoki maʼlumotlar bazasi kerak emas. Hammasi (HTML, CSS, JS, barcha til matnlari) shu bitta faylning ichida.

Papka tarkibi:
- `index.html` — platforma (asosiy fayl)
- `netlify.toml` — Netlify sozlamasi (ixtiyoriy, lekin tavsiya etiladi)
- `README.md` — shu qoʻllanma

---

## 1-usul — Drag & Drop (eng oson, hisob shart emas darajada tez)

1. https://app.netlify.com/drop sahifasini oching.
2. Shu **papkani butunligicha** (yoki ZIP faylni) sahifadagi maydonga sudrab tashlang.
3. Netlify bir necha soniyada `https://<tasodifiy-nom>.netlify.app` manzilini beradi — tayyor.
4. Nomni oʻzgartirish: **Site configuration → Change site name** (masalan `huquqshunos.netlify.app`).

> Eslatma: drag & drop'da ZIP'ni ochib tashlasangiz ham, papkani tashlasangiz ham boʻladi. Ichida `index.html` boʻlgani uchun Netlify uni avtomatik bosh sahifa qiladi.

---

## 2-usul — Netlify CLI (terminal orqali)

```bash
npm install -g netlify-cli      # bir marta
cd deploy                       # shu papka ichida
netlify deploy --prod           # soʻraganda publish dir sifatida "." ni tanlang
```

Birinchi marta `netlify login` bilan kirasiz.

---

## 3-usul — Git (GitHub/GitLab) orqali avtomatik deploy

1. Shu papkani Git repozitoriyga joylang:
   ```bash
   cd deploy
   git init && git add . && git commit -m "huquqshunos platform"
   git branch -M main
   git remote add origin <repo-url>
   git push -u origin main
   ```
2. Netlify'da **Add new site → Import an existing project → GitHub** orqali repozitoriyni tanlang.
3. Build sozlamalari:
   - **Build command:** boʻsh qoldiring (build yoʻq)
   - **Publish directory:** `.`
4. **Deploy** bosing. Bundan keyin har `git push` avtomatik yangi versiyani chiqaradi.

---

## Tekshirish
Deploy'dan soʻng saytni oching va:
- Til menyusidan **العربية** ni tanlab, boʻlim → bob → modda boʻylab yuring — barcha sarlavhalar arabcha va oʻngdan-chapga (RTL) koʻrinishi kerak.
- Boshqa tillar (uz/ru/en) ham ishlashini tekshiring.

## Yangilash
Matnni keyin oʻzgartirsangiz — yangi `index.html` ni eski oʻrniga qoʻyib, yana drag & drop qiling yoki `git push` qiling. Boshqa hech narsa shart emas.
