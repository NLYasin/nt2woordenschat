# NT2 Woordenschat

Docent NT2 opleiding için Hollandaca kavram kartları. Kantoor Woordenschat v38'in yapısı (Hatırla, Sesli tekrar, Dinle, İlerleme, çöp kutusu, hatırlatma, yedek) aynen korunur; içerik, temalar, renk ve ikon NT2'ye göre değişti. Kantoor Woordenschat'a dokunulmaz.

## Kurulum (bir kez, ~15 dakika)

1. **Supabase:** supabase.com → New project (ör. `nt2-woordenschat`). Proje açılınca **SQL Editor**'e `supabase-kurulum.sql` dosyasının tamamını yapıştır → **Run**.
2. **Adres ve anahtar:** Project Settings → API'den *Project URL* ve *publishable key*'i kopyala. `index.html` dosyasının en başındaki iki satıra yapıştır:
   ```js
   const SUPABASE_URL = 'https://PROJE-ADRESI.supabase.co';
   const SUPABASE_KEY = 'sb_publishable_ANAHTAR';
   ```
3. **GitHub:** yeni bir depo aç (ör. `nt2-woordenschat`), bu klasördeki bütün dosyaları köke yükle.
4. **Vercel:** Add New → Project → bu depoyu seç → Deploy. Ayrı bir adres alır (Kantoor'unkinden bağımsız).
5. Uygulamayı ilk açışta 97 kart veritabanına **kendiliğinden** yüklenir (üstte "İlk kurulum…" yazar). Sonra telefonda "Ana ekrana ekle".

Adres/anahtar girilmemişse üstte "Supabase ayarlanmadı" yazar.

## Kartlar

- `NT2 opleiding` sayfasından 81 ifade → grup **5 Eki**
- `Kitap ve gazete` sayfasından 16 ifade → grup **Gazete · 5 Eki**
- Hollandaca tanım → kartın açıklaması (önce Hollandaca); eş/zıt anlam ve kaynak (M1–M4, Bijeenkomst 2) → not; örnek cümleler Türkçe çevirileriyle.
- Temalar (Grupla → Tema): Leerderskenmerken, Leerroutes & inburgering, Taalgericht vakonderwijs, Nieuwkomers & doorstroom, Taalniveaus & beoordeling, Didactiek & lespraktijk, Pedagogiek & welzijn, Opleiding & reflectie, Formele & academische taal, Krant & boek.

## Yeni kelime eklemek

Ayarlar → **Claude talimatını kopyala** → kelimeleri altına yaz → Claude'a gönder → dönen JSON'u Ayarlar'daki kutuya yapıştır. Talimat artık NT2 bağlamını ve yeni temaları kullanır.

## Notlar

- Ses (TTS) Kantoor'daki Cloudflare Worker'ı kullanır. Worker belirli adreslere kısıtlıysa yeni Vercel adresini izinlilere ekle; aksi halde tarayıcı sesi devreye girer.
- Her güncellemede `sw.js` içindeki `CACHE_NAME` (şu an `nt2-woordenschat-v1`) bir artırılmalı.
- Hukuki alanlar editörde gizlidir; "Hukuki" filtresi kaldırıldı.
