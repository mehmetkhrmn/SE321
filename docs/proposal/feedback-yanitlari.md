# Proposal v1 Feedback: Yapılanlar

Hocanın v1 proposal için verdiği feedback ve [proposal-v2](proposal-v2.md) dosyasında her maddeye ne yapıldığı.

**Genel mesaj:** Kapsam ders için uygun ama çok geniş. Yeni özellik eklemek yerine **yönetilebilir bir çekirdek kapsam** tanımlayın.

| # | Feedback | v2'de yapılan | Durum |
|---|---|---|---|
| 1 | POS'un adı **KerzzPOS**, "Keraspos" değil | Her yerde KerzzPOS yazıldı | ✅ |
| 2 | Netsis asıl sorun değil; ikisini birden değiştirmek hedef olmasın | Sistem **KerzzPOS ile Netsis'in arasında** konumlandı, ikisi de yerinde kalıyor. Sınır tablosu eklendi (Bölüm 3.1) | ✅ |
| 3 | Öncelikler: cari/kasa, fatura/irsaliye, stok | Çekirdek kapsam bu sırayla 3 modül: M1 Cari ve Kasa, M2 Fatura/İrsaliye, M3 Stok (Bölüm 3.2) | ✅ |
| 4 | "Accounting management" ne demek? | **Ön muhasebe** olarak tanımlandı: tedarikçi carisi, ödeme takibi, gider kaydı, günlük kasa/kart özeti, temel raporlar. Genel muhasebe, vergi, bordro hariç; Netsis'te kalıyor | ✅ |
| 5 | AI fatura işleme: belge türü, çıkarılacak bilgi, hatalı sonuç; insan doğrulaması | Bölüm 4: belge türleri, alanlar, güven skoru, otomatik kontroller, **zorunlu "Doğrulama bekliyor" adımı**. Onaylanmayan belge stok veya cariyi değiştirmiyor. e-Fatura XML'i varsa AI'sız doğrudan okunuyor | ✅ |
| 6 | "Strong firewalls" gibi belirsiz güvenlik ifadeleri yerine ölçülebilir gereksinimler | Firewall cümlesi çıkarıldı. SEC-1..5: kimlik doğrulama, RBAC, finansal veri koruması, audit log, yedekleme (RPO 24 saat / RTO 4 saat) | ✅ (sayılar client'la teyit edilecek) |
| 7 | "Real-time" ölçülebilir tanımlanmalı | "Real-time" yerine TIM-1..3: kendi sistemimizde 5 sn, KerzzPOS verisinde [TBD] gecikme, uyarıda 1 dk. Dashboard son güncelleme saatini gösteriyor | ⚠️ KerzzPOS entegrasyon yolu öğrenilmeli |
| 8 | İş bağlamı (restoran/bar, aşçı, bar personeli, satın alma) net olmalı | Bölüm 1: Rise Group, sezonluk 3-5 şube, roller tablosu | ✅ |
| 9 | Tarih "18/10/1026" → "18/10/2026" | Düzeltildi | ✅ |
| 10 | Proje adı çok genel; daha kısa ve spesifik bir ad | Öneriler aşağıda; **grup seçecek** | ⏳ |
| 11 | Erden Can Aktan'ın ilk toplantıya katılmaması | Gruba ve hocaya yazılı açıklama gerekiyor. Repo public olduğu için burada tutulmuyor | ⏳ grup |

## 10. Proje adı

Alt başlık her durumda: *Stock, Invoice and Current-Account Management for Multi-Branch Restaurants and Bars*

| Öneri | Not |
|---|---|
| **RiseStock** | Client'ın adını taşıyor, kısa; ama sadece "stok" çağrıştırıyor |
| **StockLedger** | Stok + cari (ledger) ikisini birden anlatıyor |
| **InvoStock** | Fatura (invoice) + stok; AI fatura özelliğini öne çıkarıyor |
| **BranchBook** | Çok şubeli yapı + defter (cari/kasa) |

## Client'a sorulması gerekenler (requirements aşaması)

Bunlar v2'de [TBD] olarak işaretli:

1. KerzzPOS'tan satış verisi nasıl alınabilir? (API, otomatik export, gün sonu Excel/CSV)
2. Netsis'e veri nasıl aktarılıyor? (import dosyası, muhasebecinin elle girişi)
3. Satılan bir ürün stokta neye karşılık geliyor? Reçete var mı, yoksa ilk sürümde sadece içecek gibi doğrudan satılan ürünler mi?
4. Şube müdürü rolü var mı? Muhasebeci şirket içi mi, dışarıdan mı?
5. Tedarikçi faturalarının ne kadarı e-Fatura (XML alınabilir), ne kadarı kağıt?
6. Güvenlik sayıları (log saklama süresi, yedek saklama, RPO/RTO) client için uygun mu?
7. Başarı ölçütleri için bugünkü değerler: servis sırasında biten ürün sayısı, fatura başına harcanan süre.
