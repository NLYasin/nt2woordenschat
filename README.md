# NT2 Woordenschat — v2

Docent NT2 opleiding için Hollandaca kavram kartları (Supabase + Vercel). Kantoor Woordenschat'a dokunulmaz.

## v2 güncellemesi (zaten kurduysan)

1. Şu anki `index.html` dosyanın en başındaki **iki satırı** (SUPABASE_URL ve SUPABASE_KEY) bir yere kopyala.
2. Bu ZIP'teki dosyaları GitHub deposundaki aynı adlı dosyaların üzerine koy.
3. Yeni `index.html`'in başındaki `PROJE-ADRESI` / `ANAHTAR` satırlarını kopyaladığın iki satırla değiştir. Commit → Vercel yayınlar.
4. Uygulamayı aç. Mevcut 97 karta kelime yapısı/köken ve 2 yeni örnek cümle **kendiliğinden** eklenir. İlerleme ve tekrar takvimi değişmez, kartlar çoğalmaz.

SQL'i yeniden çalıştırmana gerek yok.

## İlk kurulum (yeni bir proje için)

1. Supabase → New project → SQL Editor → `supabase-kurulum.sql` → Run.
2. Project Settings → API'den Project URL ve publishable key'i `index.html`'in başındaki iki satıra yaz.
3. Dosyaları yeni bir GitHub deposuna yükle → Vercel'de Deploy. İlk açılışta 97 kart yüklenir.

## Kartlar

- `NT2 opleiding` sayfasından 81 ifade → grup **5 Eki**; `Kitap ve gazete` sayfasından 16 ifade → grup **Gazete · 5 Eki**.
- Her kartta: Hollandaca tanım, **3 örnek cümle** (Türkçe çevirili), **kelime yapısı ve köken**, eş/zıt anlam ve kaynak.
- Hatırla'da cevabı açınca tanım, örnekler ve kelime yapısı açık görünür; Türkçe anlam isteğe bağlı açılır.

## Yeni kelime eklemek

Ayarlar → **Claude talimatını kopyala** → kelimeleri altına yaz → Claude'a gönder → dönen JSON'u yapıştır. Talimat; tanım, yapı/köken ve 3 örnek ister.

## Notlar

- Her güncellemede `sw.js` içindeki `CACHE_NAME` (şu an `nt2-woordenschat-v2`) bir artırılmalı.
- Ses Kantoor'daki Cloudflare Worker'ı kullanır; Worker adres kısıtlıysa yeni Vercel adresini ekle.
