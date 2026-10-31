# NT2 Woordenschat — v6

Docent NT2 opleiding için Hollandaca kavram kartları (Supabase + Vercel). Kantoor Woordenschat'a dokunulmaz.

## v6 güncellemesi — ince hız ayarı

- Hız artık **0,50× ile 2,00× arasında 0,05'lik adımlarla** ayarlanır: − / + düğmeleri, kaydırma çubuğu ve hazır değerler (0,80 · 0,90 · 1,00 · 1,05 · 1,10 · 1,25).
- **Dinleme modu:** kurulum ekranında tam ayar; oynatırken de cümlenin altında − / + ile değiştirilebilir (bir sonraki tekrarda geçerli olur).
- **Sesli tekrar, kartlar ve Hatırla'daki dinle düğmeleri:** Sesli tekrar ekranının üstündeki ve Ayarlar → Görünüm'deki **Ses hızı**. Varsayılan 0,90× (önceki sabit hız ile aynı).
- İki hız ayrı tutulur ve cihazda hatırlanır.

## v5 güncellemesi

1. ZIP'teki bütün dosyaları GitHub deposundaki aynı adlı dosyaların üzerine koy ve commit et. Supabase adresi ve anahtarı `index.html` içinde hazır.
2. Uygulamayı aç. **NT2 Docententaal** belgesindeki 168 kart kendiliğinden eklenir (üstte "Docententaal: … cümle ekleniyor" yazar).
   - 167 sınıf cümlesi (12 bölüm) + ilk ders için örnek açılış konuşması.
   - Grup **31 Eki**, tema **Docententaal in de klas**, tür **Cümle**.
   - Not alanında bölüm adı; "even / maar / eens" yumuşatıcıları ve je/jullie hitabı için kısa ipucu.
   - Belgede iki kez geçen "Neem rustig de tijd." bir kez eklendi.
3. Ekleme sunucuda bir kez kaydedilir; başka cihazda açınca kartlar çoğalmaz. Mevcut ilerleme değişmez.

SQL'i yeniden çalıştırmana gerek yok.

## İlk kurulum (yeni bir proje için)

1. Supabase → New project → SQL Editor → `supabase-kurulum.sql` → Run.
2. Project Settings → API'den Project URL ve publishable key'i `index.html`'in başındaki iki satıra yaz.
3. Dosyaları yeni bir GitHub deposuna yükle → Vercel'de Deploy. İlk açılışta 97 kart yüklenir.

## Kartlar

- `NT2 opleiding` sayfasından 81 ifade → grup **5 Eki**; `Kitap ve gazete` sayfasından 16 ifade → grup **Gazete · 5 Eki**.
- Her kartta: Hollandaca tanım, **3 örnek cümle** (Türkçe çevirili), **kelime yapısı ve köken**, eş/zıt anlam ve kaynak.
- Hatırla'da cevabı açınca tanım ve örnekler görünür; Türkçe anlam, kelime yapısı/köken ve notlar "Türkçe anlam ve notlar" açılınca görünür.

## Yeni kelime eklemek

Ayarlar → **Claude talimatını kopyala** → kelimeleri altına yaz → Claude'a gönder → dönen JSON'u yapıştır. Talimat; tanım, yapı/köken ve 3 örnek ister.

## Notlar

- Her güncellemede `sw.js` içindeki `CACHE_NAME` (şu an `nt2-woordenschat-v6`) bir artırılmalı.
- Ses Kantoor'daki Cloudflare Worker'ı kullanır; Worker adres kısıtlıysa yeni Vercel adresini ekle.
