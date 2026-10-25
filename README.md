# SE321: Çok Şubeli Restoran için Stok, Fatura ve Cari Takip Sistemi

SE321 yazılım tasarımı dersi projesi (Section 2 - Group 2). Client: **Rise Group** (çok şubeli restoran/bar, Financial Director).

**Çekirdek kapsam** ([proposal v2](docs/proposal/proposal-v2.md)): KerzzPOS (satış) ile Netsis (muhasebe) arasında çalışan, ikisinin yerine geçmeyen bir sistem:
1. Cari ve kasa yönetimi (ön muhasebe)
2. Fatura / irsaliye işleme (AI destekli okuma + zorunlu insan doğrulaması)
3. Stok yönetimi (çok şube)

## Klasör yapısı

```
docs/
├── proposal/
│   ├── proposal-v2.md                       # Feedback sonrası revize proposal (İngilizce)
│   └── feedback-yanitlari.md                # Feedback maddeleri ve yapılanlar, client'a açık sorular
├── interview/
│   ├── semi-structured-interview-agaci.md   # Client görüşmesi soru ağacı (31 soru, 8 dal)
│   └── gorusme-notlari.md                   # Görüşme sırasında/sonrasında doldurulacak notlar
└── notlar/
    └── 2026-10-14-konusma-ozeti.md          # Proje başlangıç özeti
```

## Yol haritası

- [x] Gereksinim toplama görüşmesi için soru ağacını hazırlamak
- [x] İlk client toplantısı (15.10.2026) ve proposal v1
- [ ] Proposal'ı feedback'e göre revize etmek (v2 taslağı hazır; proje adı ve [TBD]'ler kaldı)
- [ ] Açık soruları client'a sormak, notları `docs/interview/gorusme-notlari.md` dosyasına işlemek
- [ ] Gereksinim listesi (fonksiyonel / fonksiyonel olmayan, MoSCoW)
- [ ] User story ve use case'ler (Mal Kabul, Stok Sayımı, Fire Kaydı, Sipariş Oluşturma)
- [ ] Tasarım: use case, sınıf, sequence diyagramları; mimari
- [ ] Prototip
