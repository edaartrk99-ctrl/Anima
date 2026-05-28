# 🚀 Vercel Deploy Öncesi Son Adımlar

Bu dosya proje klonlandıktan sonra yapılması gereken adımları detaylı olarak açıklıyor.

## 1️⃣ AnimaApp.jsx'i güncelleyin

`components/AnimaApp.jsx` dosyasında API çağrılarını backend'e yönlendirmelisiniz.

**Nerede:** Dosyanın ~205-315. satırları arası

**Yapılacak:** Aşağıdaki iki fonksiyonu bu şekilde değiştirin:

```javascript
// ─── API EGZERSİZ ÇAĞRISI ─────────────────────────────────────────────────────
// ESKI: Doğrudan Claude API'ye çağrı yapıyordu
// YENİ: Backend'e (pages/api/exercise.js) çağrı yapıyor

async function fetchDailyExercise({ mood, journey, weekTheme, day, ratings }) {
  const moodLabel = MOODS.find(m => m.v === mood)?.l || mood;

  try {
    const res = await fetch("/api/exercise", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({
        mood: moodLabel,
        journey,
        weekTheme,
        day,
        ratings,
      }),
    });

    if (!res.ok) throw new Error("API çağrısı başarısız");
    return await res.json();
  } catch (error) {
    console.error("Exercise API error:", error);
    throw error;
  }
}

// ─── HAFTALıK ÖZET API ÇAĞRISI ─────────────────────────────────────────────────
async function fetchWeeklyInsight({ journey, weekTheme, ratings }) {
  try {
    const res = await fetch("/api/weekly", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({
        journey,
        weekTheme,
        ratings,
      }),
    });

    if (!res.ok) throw new Error("API çağrısı başarısız");
    return await res.json();
  } catch (error) {
    console.error("Weekly API error:", error);
    throw error;
  }
}
```

---

## 2️⃣ .env.local dosyasını oluştur

`.env.local.example`'ı kopyala:

```bash
cp .env.local.example .env.local
```

Sonra `.env.local`'a Claude API Key'ini ekle:

```
ANTHROPIC_API_KEY=sk-ant-v0-your_actual_api_key_here
```

---

## 3️⃣ Lokal test et

```bash
npm install
npm run dev
```

`http://localhost:3000` açış ve uygulamayı test et.

---

## 4️⃣ GitHub'a push et

```bash
git add .
git commit -m "Initial commit: Anima app ready for deploy"
git push origin main
```

---

## 5️⃣ Vercel'e deploy et

1. https://vercel.com sitesine git
2. "New Project" → GitHub bağla
3. `anima-app` repo'sunu seç
4. **Environment Variables** bölümüne `ANTHROPIC_API_KEY` ekle
5. Deploy başlasın

---

## ✅ Deploy Kontrol Listesi

- [ ] AnimaApp.jsx API çağrıları güncellenmiş
- [ ] .env.local oluşturulmuş ve API key eklenmişse
- [ ] `npm run dev` lokal'de çalışıyor
- [ ] GitHub'a push edilmiş
- [ ] Vercel bağlanmış
- [ ] Environment variable'lar Vercel'de ayarlanmış
- [ ] Deploy başlamış
- [ ] Live URL'de çalışıyor

---

## 🧪 Test etme

Deploy sonrası:
1. Live URL'yi aç
2. Onboarding'den geç
3. Sabah ekranında bir duygu seç
4. "Günüme başla" de
5. API'den egzersiz gelip gelmediğini kontrol et

API çağrısı başarısız olursa → Vercel logs'u kontrol et:
```
Vercel Dashboard → Deployments → Logs → Function Logs
```

---

**İhtiyaç halinde:** Sorularını GitHub Issues'a aç veya Anthropic API docs'ları kontrol et.

Good luck! 🚀
