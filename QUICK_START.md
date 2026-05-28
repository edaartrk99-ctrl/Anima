# ⚡ ANIMA — 5 Dakikalık Kurulum

Tamam, işte en basit adımlar:

---

## 1️⃣ Klasörü indir ve aç
Bu klasörü indirip terminalinde aç:
```bash
cd anima-nextjs-complete
```

---

## 2️⃣ Bağımlılıkları yükle
```bash
npm install
```

---

## 3️⃣ API Key'ini ekle

`.env.local.example` dosyasını `.env.local` olarak yeniden adlandır:

```bash
# macOS/Linux
cp .env.local.example .env.local

# Windows
copy .env.local.example .env.local
```

Sonra `.env.local` dosyasını aç ve şuna ekle:
```
ANTHROPIC_API_KEY=sk-ant-v0-YOUR_ACTUAL_KEY_HERE
```

(KEY'i [console.anthropic.com](https://console.anthropic.com) adresinden al)

---

## 4️⃣ Çalıştır
```bash
npm run dev
```

Tarayıcıda aç: **http://localhost:3000**

Bitti! Anima lokal'de çalışıyor. ✨

---

## 🚀 Vercel'e Yükle (Opsiyonel)

Eğer internete koymak istersen:

1. GitHub hesabı aç
2. Bu klasörü GitHub'a yükle
3. [Vercel.com](https://vercel.com) git
4. "New Project" de → GitHub'ı seç → anima-nextjs-complete'i seç
5. Environment Variable:
   - Key: `ANTHROPIC_API_KEY`
   - Value: Senin API key'in
6. Deploy!

Bitti! URL'in gelmesi 1-2 dakika alır.

---

## 🧪 Test

1. Sayfada "Başla" ya bas
2. 5 soruyu yanıtla
3. Yolculuk seç
4. Sabah ekranında duygu seç
5. "Günüme başla" de
6. API'den egzersiz geliyor mu?

Evet mi? Tamamdır! 🎉

---

## 🆘 Sorun mu?

**"Cannot find module"?**
```bash
rm -rf node_modules
npm install
```

**API timeout?**
- API key doğru mu kontrol et
- İnternet bağlantısı var mı?

**Vercel'de hata?**
- Vercel Dashboard → Deployments → Logs bak
- API key'in Vercel'e eklenmiş mi kontrol et

---

**Hepsi tamam? Başarılar!** 🚀
