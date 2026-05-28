# Anima — Psikolojik Dayanıklılık Uygulaması

Modern psikoloji ve İslam psikolojisini sentezleyen, BDT temelli self-help uygulaması.

## 🚀 Hızlı Başlangıç

### 1. Repo'yu klonla
```bash
git clone https://github.com/username/anima-app.git
cd anima-app
```

### 2. Bağımlılıkları yükle
```bash
npm install
```

### 3. Ortam değişkenlerini ayarla
`.env.local` dosyasını oluştur:
```
ANTHROPIC_API_KEY=your_api_key_here
```

**Not:** `.gitignore`'da `.env.local` zaten var, public'e exposed olmayacak.

### 4. Lokal olarak çalıştır
```bash
npm run dev
```

Tarayıcıda `http://localhost:3000` açısına.

---

## 📦 Proje Yapısı

```
anima-app/
├── pages/
│   ├── api/
│   │   ├── exercise.js          # Günlük egzersiz API
│   │   └── weekly.js            # Haftalık özet API
│   ├── _app.js                  # Global wrapper
│   ├── _document.js             # HTML başlığı
│   └── index.js                 # Ana sayfa
├── components/
│   └── AnimaApp.jsx             # Ana uygulama componenti
├── styles/
│   └── globals.css              # Global CSS
├── package.json
├── next.config.js
└── .env.local.example
```

---

## 🔑 Claude API Key'i Vercel'e ekleme

1. Vercel Dashboard → Project Settings
2. Environment Variables
3. `ANTHROPIC_API_KEY` ekle (değeri gizli kalıyor)

---

## 🚢 Vercel'e Deploy

### GitHub üzerinden:
1. Repo'yu GitHub'a push et
2. Vercel sitesine git
3. "New Project" → GitHub'ı connect et → anima-app'ı seç
4. Otomatik deploy başlayacak
5. Environment Variable `ANTHROPIC_API_KEY`'i ekle

**Deploy artık otomatik:** her push'da main branch yeniden deploy olur.

---

## 💻 Teknoloji Stack

- **Framework:** Next.js 14
- **UI:** React 18 (native CSS)
- **AI:** Claude Sonnet 4 (Anthropic)
- **Storage:** Browser's window.storage API
- **Deploy:** Vercel

---

## 📝 Notlar

- Storage browser'da kalıyor → her cihazda ayrı ilerleme
- API Key'ler backend'te gizli tutuluyor (next.js routes)
- Mobil-first tasarım (375px viewport)
- Dark mode fixed

---

## 🛠️ Geliştirme

Lokal dev'de değişiklikleri yap, git push et → Vercel otomatik deploy eder.

```bash
npm run build   # Production build test
npm start       # Production server
```

---

## 📞 Support

Sorunlar veya feedback için GitHub Issues'ı aç.

---

Made with ❤️ for psychological resilience
