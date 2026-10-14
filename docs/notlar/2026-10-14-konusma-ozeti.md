# SE321 Projesi: Konuşma Özeti

**Tarih:** 14 Ekim 2026
**Proje:** SE321 yazılım tasarımı dersi projesi
**Client:** Bir restoran
**Varsayılan proje fikri:** Stok (envanter) takip sistemi

---

## 1. Ne konuştuk?

| Konu | Sonuç |
|---|---|
| Client ile interview | Gerçek bir client ile **semi-structured** bir gereksinim toplama görüşmesi yapılacak. Bunun için ağaç şeklinde bir soru şeması hazırlandı. |
| Client'ın alanı | Client'ın bir **restoran** olduğu, odak noktasının da **stok takibi** olabileceği belirtildi. Soru ağacı buna göre özelleştirildi. |
| Repo | **SE321** GitHub reposu (`mehmetkhrmn/SE321`) projeye eklendi. Bundan sonraki çalışmalarda kullanılabilir. |
| Cloud session | Proje ve thread'ler Claude'un **bulutta** çalışan oturumları (Claude Code on the web). Kendi bilgisayarında değil, Anthropic'in geçici bir sunucusunda çalışıyor. |
| Ücretlendirme | Ayrıca dolar kesilmiyor; kullanım claude.ai aboneliğinin (Pro/Max) limitlerinden düşüyor. Hesapta **extra usage** açıksa limit dolunca ücret çıkabilir. Kontrol yeri: **Settings > Usage**. (Genel bilgi; plan buradan görülemedi.) |

---

## 2. Interview Soru Ağacı (özet)

Dosya: [semi-structured-interview-agaci.md](../interview/semi-structured-interview-agaci.md)

Önce genel bir gereksinim toplama ağacı yazıldı, sonra restoran ve stok takibine göre güncellendi. Toplam **8 dal, 31 ana soru**, her ana sorunun altında follow-up (F) ve probe (P) soruları var. Süre hedefi **45-60 dakika**.

| Dal | Süre | Neyi soruyor? |
|---|---|---|
| **A. Açılış ve tanışma** | ~5 dk | Restoranın türü, şube/personel sayısı, stokla ilgili en büyük sıkıntı |
| **B. Mevcut stok süreci** | ~12 dk | Stoğun yolu adım adım: mal kabul, depolama, sayım, sipariş, tüketim (reçete), fire ve son kullanma tarihi |
| **C. Kullanıcılar ve paydaşlar** | ~6 dk | Roller (sahip, müdür, aşçı, depocu), yetkiler, mutfakta hangi cihazla kullanılacağı |
| **D. Fonksiyonel gereksinimler** | ~12 dk | Must/Should/Could önceliği, malzeme bilgileri ve birim dönüşümü (koli/kg/adet), kritik stok uyarısı, sipariş önerisi, raporlar, POS entegrasyonu, çok şube |
| **E. Fonksiyonel olmayan gereksinimler** | ~6 dk | Cihaz ve internet durumu, kullanım hızı, hassas veriler ve log, gıda güvenliği kayıtları |
| **F. Kısıtlar ve riskler** | ~5 dk | Bütçe, daha önce denenmiş programlar, personelin veri girmemesi riski |
| **G. Başarı kriterleri** | ~4 dk | 6 ay sonra neyin değişmiş olması gerektiği, MVP |
| **H. Kapanış** | ~5 dk | Eksik konular, örnek belgeler (fatura, sayım listesi, reçete), depo/mutfak turu, özet ve onay |

**Dosyada ayrıca şunlar var:**
- Görüşme öncesi hazırlık (yoğun saat dışında ve restoranda görüşmek, rol dağılımı, kayıt izni, depo sorumlusuyla da konuşmak)
- Semi-structured yöntem ipuçları: huni tekniği, probe kalıpları, kaçınılacak sorular
- Restorana özel dikkat noktaları: birim karmaşası ve reçete için mutlaka somut örnek istemek, fire konusunu suçlayıcı olmayan bir tonla sormak
- Görüşme sonrası adımlar: MoSCoW önceliklendirme, user story ve use case taslakları (Mal Kabul, Stok Sayımı, Fire Kaydı, Sipariş Oluşturma), client'tan onay
- Görüşmede doldurulacak not şablonu tablosu

Client stok yerine başka bir sorunu (adisyon, rezervasyon, vardiya) öne çıkarırsa diye sorular açık uçlu bırakıldı.

---

## 3. Sıradaki adımlar

1. Interview'u soru ağacıyla yapmak ve notları şablona işlemek.
2. Notlardan gereksinim listesi, user story ve use case'leri çıkarmak.
3. Yazılım tasarımını (diyagramlar, mimari) SE321 reposunda geliştirmek.
