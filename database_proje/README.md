Kişisel Veri İçgörü Üretimi

n8n üzerinde çalışan, yapay zeka destekli otomatik haber özeti ve kişisel içgörü üretim iş akışı.

Proje Hakkında

Bu proje, dünya ve teknoloji haberlerini iki farklı RSS kaynağından çekerek OpenAI GPT-4.1-mini modeliyle özetleyen ve isteğe bağlı olarak Gmail üzerinden e-posta gönderen bir n8n otomasyon iş akışıdır.

İş Akışı Mimarisi

```
Manuel Tetikleyici
       |
       v
AI Özet Ajanı  <── OpenAI GPT-4.1-mini (Dil Modeli)
       ^               ^
       |               |
  Tech Haberleri   Dünya Haberleri
  (The Verge RSS)  (BBC World RSS)
       |
       v
 Haber Özeti Çıktısı
       |
       v
 Gmail ile Gönder (İsteğe Bağlı)
```

Özellikler

- Otomatik haber toplama — The Verge (teknoloji) ve BBC World (dünya) RSS beslemelerinden
- AI destekli özetleme — GPT-4.1-mini ile son 24 saatin önemli gelişmeleri
- Akıllı filtreleme — Üzücü veya rahatsız edici haberler otomatik olarak elenır
- E-posta gönderimi — Gmail entegrasyonu ile özet doğrudan gelen kutunuza
- Esnek çıktı — Haber özeti ayrı bir Set node'unda da saklanabilir

Kurulum

Gereksinimler

- [n8n](https://n8n.io/) (self-hosted veya cloud)
- OpenAI API anahtarı
- Gmail hesabı (opsiyonel, e-posta adımı için)

Adımlar

1. Bu repoyu klonlayın:
   ```bash
   git clone https://github.com/KULLANICI_ADINIZ/kisisel-veri-icgoru-uretimi.git
   ```

2. `AI_Agent_workflow.json` dosyasını n8n'e aktarın:
   - n8n arayüzünde Workflows > Import from file seçin
   - JSON dosyasını yükleyin

3. OpenAI Model node'unu açın ve kendi OpenAI API credentials'ınızı bağlayın.

4. (Opsiyonel) Send summary with Gmail node'unu açın ve Gmail hesabınızı bağlayın.

5. İş akışını Manuel Tetikleyici ile çalıştırın.

Kullanım

- İş akışını manuel olarak tetiklemek için n8n arayüzünde Test workflow butonuna tıklayın.
- Otomatik çalıştırmak için Manual Trigger yerine bir Schedule Trigger node'u ekleyebilirsiniz (örneğin her sabah 08:00).

Notlar

- Kimlik bilgileri (API anahtarları) bu repoya dahil edilmemiştir. Her kullanıcı kendi credentials'larını n8n üzerinden bağlamalıdır.
- İş akışı n8n `v1` execution order ile çalışmaktadır.

Lisans

MIT
