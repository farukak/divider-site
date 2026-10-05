# Divider — tanıtım sayfası

Tek sayfalık, bağımlılıksız statik site (`index.html` + `privacy.html` + `assets/`).
Herhangi bir statik barındırmaya olduğu gibi yüklenir (GitHub Pages, Cloudflare Pages,
Netlify, S3+CloudFront, Vercel). Derleme adımı yok.

Yerelde bakmak için:

    python3 -m http.server 8765 --bind 127.0.0.1 --directory divider-site

## Yayından önce doldurulacaklar

- **App Store bağlantısı**: `index.html` içinde iki yerde `class="store soon"` olan
  `<a href="#download">` -> gerçek `https://apps.apple.com/app/id<ID>` adresi; `soon`
  sınıfını ve `İNCELEMEDE/SOON` etiketini kaldır; metni "Yakında" -> "İndirin".
- **Google Play bağlantısı**: `https://play.google.com/store/apps/details?id=com.trt.divider`
  (paket adı sabit; uygulama yayınlanınca çalışır).
- **APK**: Site üzerinden APK dağıtılmaz (karar: 2026-10-05). İndirme yalnızca Google Play
  ve App Store üzerinden; `downloads/` klasörü depodan kaldırıldı.
- **Gizlilik iletişim e-postası**: `privacy.html` (kaynağı `../PRIVACY.md`) içindeki
  `<buraya iletişim e-postanız>` yer tutucusu.
- **og:image / canonical**: `<meta property="og:image">` göreli yol; alan adı belli olunca
  tam URL yap ve `<link rel="canonical">` ekle.

## İçerik

- TR/EN: her metin `data-tr` / `data-en` özniteliklerinde; sağ üstteki anahtar
  `localStorage` ile hatırlanır. Varsayılan TR.
- Hero'daki telefon canlı demodur (iki uygulama seç, üst üste / yan yana geçişi).
- Ekran görüntüleri gerçek cihazlardan: Android 15 emülatörü (ana ekran, bölünmüş ekran,
  açılış) ve iPhone 16e simülatörü (dikey 2 panel, yatay yan yana).
