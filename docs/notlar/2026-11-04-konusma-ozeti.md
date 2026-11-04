# SE321 Projesi: Konuşma Özeti (2)

**Dönem:** 14 Ekim – 4 Kasım 2026
**Proje:** SE321 yazılım tasarımı dersi projesi (Section 2 - Group 2)
**Client:** Mustafa Ulukaya, Financial Director, Rise Group (çok şubeli restoran/bar)
**Önceki özet:** [2026-10-14-konusma-ozeti.md](2026-10-14-konusma-ozeti.md)

Bu dosya, proje üzerinde Claude ile yapılan çalışma oturumunun özetidir. Ne yapıldı, hangi kararlar alındı, ne kaldı.

---

## 1. Ne yapıldı?

| Konu | Sonuç | Dosya |
|---|---|---|
| Repo kurulumu | Boş repoya README, soru ağacı ve ilk konuşma özeti eklendi. | [README.md](../../README.md) |
| Soru ağacı güncellemesi | "Restoran 2 sistem kullanıyor, biri ~30 yıllık" bilgisi üzerine **B+. Mevcut Sistemler** dalı (S1–S7) eklendi. | [semi-structured-interview-agaci.md](../interview/semi-structured-interview-agaci.md) |
| Proposal v1 feedback'i | Hocanın 11 maddelik feedback'i madde madde ele alındı. | [feedback-yanitlari.md](../proposal/feedback-yanitlari.md) |
| Görüşme kaydı | 15.10 görüşmesinin 25 dakikalık ses kaydı otomatik transkripte çevrildi; Netsis, Kerzz, soft içecek gibi yanlış yazımlar düzeltildi. Transkript client bilgisi içerdiği için repoya konmadı. | - |
| Görüşme notları | Kayıttan çıkan bilgiler not şablonuna işlendi (roller, iş akışı, mevcut sistemler, öncelikler, açık sorular). | [gorusme-notlari.md](../interview/gorusme-notlari.md) |
| Proposal v2 | Önce ayrıntılı bir taslak, sonra şablon formatında **kısa teslim versiyonu** yazıldı. Problem ve çözüm bölümleri kayda ve feedback'e göre düzeltildi. | [proposal-v2.md](../proposal/proposal-v2.md), [proposal-v2-detayli.md](../proposal/proposal-v2-detayli.md) |
| Kararlar | Grubun kapsam ve tasarım kararları kaydedildi (K1–K3). | [kararlar.md](../kararlar.md) |
| Gereksinimler v1 | Kayıttan 14 FR ve 9 NFR çıkarıldı; her biri zaman damgalı alıntıyla (Türkçe). | [gereksinimler-ilk-gorusme.md](../requirements/gereksinimler-ilk-gorusme.md) |
| Gereksinimler v2 | Maddeler bölünüp mevcut iş akışından yeni maddeler eklenerek 40 FR ve 19 NFR'ye genişletildi; [Açık] / [Süreç] etiketleri (Türkçe). | [gereksinimler-ilk-gorusme-v2.md](../requirements/gereksinimler-ilk-gorusme-v2.md) |
| Gereksinimler v3 | Ders formatında İngilizce: "The system shall …", kaynak, H/M/L öncelik, Stated/Assumed/Proposed; özet, aktörler, kısıtlar, açık sorular. 43 FR, 18 NFR. | [requirements-v3.md](../requirements/requirements-v3.md) |
| Gereksinimler v3 kısa | 15 FR, 8 NFR (6 kategori). Tüm kaynaklar kayda dayanıyor; "Team proposal" kaynağı kullanılmadı, Proposed madde yok. | [requirements-v3-short.md](../requirements/requirements-v3-short.md) |

## 2. Alınan kararlar

| # | Karar | Gerekçe |
|---|---|---|
| K1 | Yeni sistem **KerzzPOS'un yerine geçecek**; **Netsis** resmi muhasebe olarak kalacak, onaylı kayıtlar Netsis'e aktarılacak. | Veri tek yerde doğsun, üçüncü bir sistem eklenmesin. Hoca ikisini birden değiştirmememizi istedi; client Netsis'ten memnun. |
| K2 | Yeni POS, client'ın KerzzPOS'ta beğendiği yanları (ayrıntılı ciro ve kasa raporları) koruyacak. | Client Kerzz'in raporlamasını övdü; "ciro, kasa programı" korunmalı dedi. |
| K3 | Yazarkasa (ÖKC) bağlantısı **simüle edilecek** (mali cihaz arayüzü + sahte modül). | Gerçek cihaz bağlantısı bir dönemlik projede gerçekçi değil. Proposal'ı değil, requirements ve tasarım aşamasını ilgilendiriyor. |
| - | Proposal **kısa ve net** olacak; ayrıntılı güvenlik ve süre tabloları requirements aşamasına bırakıldı. | Hoca bunları "in the requirements stage" için istedi. |
| - | Proje adı için **özel ad + açıklayıcı alt başlık** yapısı. | Hoca kısa ve spesifik bir ad önerdi; yazılım projelerinde yaygın yapı bu. |

## 3. Görüşme kaydından öne çıkanlar

- Client'ın ilk üç önceliği: **(1) cari ve kasa, (2) fatura/irsaliye, (3) stok.**
- **Fatura işleme "en büyük problem":** haftada 70-80 fatura, her faturada farklı iskonto, PDF'ten otomatik işlenmesi isteniyor.
- **Netsis'te sorun yok.** Sorun KerzzPOS ile Netsis'in birbiriyle konuşmaması; veri Excel ile elle taşınıyor.
- KerzzPOS'taki stok "%100 doğru değil", kritik stok uyarısı yok; aylık sayım 1-2 kişiyle 4-5 saat sürüyor, haftalık olması isteniyor.
- **İş akışı:** barmen ve şef WhatsApp grubuna talep yazıyor → satın alma onaylıyor → depo sorumlusu malı kapıda teslim alıyor → satın alma müdürü veriyi giriyor.
- **İrsaliye:** client öncelik listesinde saydı (~25:06) ve bugün teyit için kullanılıyor (~05:01–05:08). **Otomatik okuma sadece fatura için istendi.** İrsaliye için "kayıt ve teyit" yeterli görünüyor; proposal'daki ilgili cümlenin buna göre düzeltilmesi önerildi.
- Client mevcut POS'un güvenliğini zayıf buluyor; personelin yeni sisteme alışma süresi 15 gün - 1 ay.

## 4. Kalan işler

**Teslimden önce**
1. **Proje adını seçmek.** Belgelerde hâlâ `[PROJECT NAME]` yazıyor. Öneriler: RiseOne (önerilen), TableLedger, RestoLedger, ServeStock.
2. Proposal'a öğrenci numaraları, e-postalar ve toplantı fotoğrafı eklenecek (repo public olduğu için repoda yok).
3. Erden Can Aktan'ın ilk toplantıya katılmamasıyla ilgili açıklama hocaya yazılacak.
4. Proposal'daki "invoices and delivery notes … extracts" cümlesi, sadece faturanın otomatik okunacağı şekilde düzeltilebilir (karar bekliyor).

**Requirements aşaması**
5. Uzun v3'teki 5 Proposed madde hâlâ "Team proposal" kaynaklı; kısa versiyondaki gibi düzeltilmesi gerekip gerekmediği karar bekliyor.
6. Kısa v3'te güvenlik tek maddeye düştü (yetkili roller). Kimlik doğrulama ve audit log ancak Proposed olarak, gerekçesiyle geri eklenebilir.
7. Uzun v3'te NFR-17 (`[N]` sipariş/saat) bilinmiyor; ya sorulmalı ya da sadece açık sorulara bırakılmalı.

**İkinci client görüşmesi**
8. Requirements v3'teki Open Questions listesi soru listesi olarak kullanılacak. Başlıca sorular:
   - Şubeler arası transfer var mı? (Kayıtta çelişkili.)
   - Mal kabulünü sisteme kim girecek?
   - Hangi Kerzz raporları korunmalı? Ekran görüntüleri alınabilir mi?
   - Reçete var mı?
   - Fiyatları kim görmeli?
   - Hangi yazarkasa cihazı kullanılıyor?
   - Netsis hangi formatta veri alıyor?
   - Gıda denetimi için hangi kayıtlar tutulmalı?
   - İrsaliyeler de otomatik okunsun mu?

## 5. Notlar

- **Repo public.** Öğrenci numaraları, e-postalar, ham transkript, client'ın ödediği ücret tutarları ve geçmişteki güvenlik olayının ayrıntısı bu yüzden repoda yok. Repo private yapılırsa eklenebilir.
- **Transkript sınırları:** Otomatik transkript küçük bir modelle üretildi. Kelime hataları var, konuşmacı ayrımı yok (Client/Ekip etiketleri bağlamdan çıkarıldı). Yaklaşık 09:31–10:00 arası tam değil.
