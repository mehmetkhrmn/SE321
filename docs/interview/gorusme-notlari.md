# Client Görüşmesi: Notlar

**Tarih:** 15.10.2026 (kayıt 17:22, ~25 dk)
**Görüşülen kişi:** Mustafa Ulukaya, Financial Director, Rise Group. Ağırlıklı olarak muhasebe ve finanstan sorumlu; hafta sonları işletmeye de destek veriyor.
**Kaynak:** Ses kaydının otomatik transkripti (Whisper small). Transkript kelime düzeyinde hatalı olabilir; tırnak içindeki sözler kayda göre **yaklaşık** aktarımdır. Ham transkript, client bilgileri içerdiği için public repoda tutulmuyor.

Soru numaraları [soru ağacındaki](semi-structured-interview-agaci.md) numaralardır. Dakikalar kayıttaki zamanı gösterir.

> Repoda tutulmayan iki bilgi daha var: client'ın ödediği/ödeyebileceği aylık ücret ve geçmişte yaşanan bir güvenlik olayı. Repo private yapılırsa eklenebilir.

---

## Özet tablo

| Bölüm | Önemli cevaplar | Pain point | Gereksinim | Açık soru |
|---|---|---|---|---|
| A. Açılış | Yazın 4-5, kışın 3 işletme; yılda ~250 personel | | Çok şube, sezonluk açılıp kapanan şube | |
| B. Mevcut stok süreci | Sipariş WhatsApp grubundan, haftalık; mal kabulü depo sorumlusu yapıyor; sayım aylık, 4-5 saat | Fatura işleme "en büyük problem"; kritik stok uyarısı yok; fire/SKT manuel | Fatura PDF'inden otomatik işleme; kritik stok uyarısı; haftalık sayım | |
| B+. Mevcut sistemler | KerzzPOS + Netsis, entegrasyon yok; Netsis'te sorun yok | İki sistem konuşmuyor; Kerzz stoğu %100 doğru değil; Kerzz güvenliği zayıf | Kerzz → stok → Netsis veri akışı | Hangisi 30 yıllık? Veri nasıl dışarı alınır? |
| C. Kullanıcılar | Satın alma müdürü veri girer; depo sorumlusu veri girmez | | Roller: satın alma, depo, mutfak, bar, finans | Şube müdürü var mı? |
| D. Fonksiyonel | İlk 3: cari ve kasa, fatura/irsaliye, stok | | Must: cari, kasa, fatura/irsaliye, stok | Reçete var mı? |
| E. Fonks. olmayan | Mutfak, telefon, ofis; ürünler uzun süre durmuyor | | Mobil kullanım; güvenlik | Gıda denetimi için hangi kayıt? |
| F. Kısıtlar | Mevcut sisteme kurulum + aylık bakım ücreti ödeniyor | Ödeme gecikince sistem kapatılıyor | | |
| G. Başarı | Alışma süreci 15 gün - 1 ay | | Eğitim, kolay arayüz | Başarı metriği? |

---

## Ayrıntılı notlar

### A. Açılış ve tanışma (00:00-01:15)

- Şube: "yazın aktif olarak 4-5, kışın 3 işletme var". Yılda toplam ~250 personel.
- Hiyerarşi: mutfakta şef, onun üstünde **satın alma müdürü**; **depo sorumlusu**; **komi, garson, barboy** altta. Barda **barmen**.
- En büyük problem: "fatura geldiğinde o faturayı işlemek bizim için çok büyük bir problem." Yazın şubeler açılınca fatura sayısı birden artıyor.
- Dile getirilen fikir: "Fatura geldi, PDF şeklinde içine attık; direkt Netsis'e ya da herhangi bir yere işleyebiliyorsa…"

### B. Mevcut stok süreci

**Mal kabul (04:11-05:41)**
- Malzemeyi depo sorumlusu (ve satın alma) karşılıyor. Örnek: "iki koli Chivas 18 geldi."
- Kapıda teslim alınıyor; **hem tedarikçi hem işletme kaşe-imza** atıyor.
- Ürün ya barın içine ya da **-2. kattaki depoya** alınıyor.
- Mal geldiği **WhatsApp üzerinden** bildiriliyor; irsaliye fotoğrafıyla teyit ediliyor.
- Bozuk mal → **iade** süreci.

**Stok takibi (02:06-02:33, 06:04-06:42)**
- KerzzPOS'tan satışlar çekilip **Excel'e** aktarılıyor; alış faturaları Kerzz'e giriliyor.
- Kerzz'de stok, satış tuşlandıkça alış faturalarından düşüyor; ama "yüzde yüz verilerle takip edilmiyor."
- Netsis'e bu veriler **işlenmiyor**.

**Sipariş kararı (02:33-03:20)**
- **Haftalık planlama.** Bir **WhatsApp grubu** üzerinden: barmen (alkol, soft içecek) ve mutfak şefi talebini yazıyor, **satın alma onaylıyor**.
- Kerzz'de ürün bitince uyarı gelmiyor. İstek: "soft içecekler 50'nin altına düştü" gibi bir **uyarı**.

**Birim (07:44-08:00)**
- Koli geliyor, şişe sayısına **çarpılarak** tutuluyor → birim dönüşümü gerekli.

**Fire / bozulma / SKT (03:22-03:27, 19:44-20:32)**
- **Manuel** kontrol.
- Ürünler haftalık ya da aylık tüketiliyor, "bozulacak kadar durmuyor". Uzun süreli stok yok.

**Mal giriş sıklığı ve fatura hacmi (18:14-18:56)**
- Mal haftada iki gün geliyor (ör. salı-cuma); hafta sonu iş yoğun.
- "Bu hafta gelen fatura 76." **Haftada 70-80 fatura** (alkol, soft içecek, çerez, gıda…).
- Faturalarda **iskonto** var ve her seferinde aynı değil (19:22-19:32) → fatura okumada iskonto alanı gerekli.

**Sayım (17:09-17:44)**
- **Aylık**, 1-2 kişi, **4-5 saat**.
- "Bu sistemle **haftalık** olsa süper olur."

### B+. Mevcut sistemler (01:37-11:48)

| | KerzzPOS | Netsis |
|---|---|---|
| Ne için | POS, adisyon, satış, kasa/kart raporları; alış faturası girilerek basit stok | Muhasebe: faturalar (portal üzerinden), cari dökümü |
| Memnuniyet | Raporlama çok ayrıntılı ("istediğin her raporu veriyor"); alternatiflerden daha donanımlı | "Netsis'te problem yok", "şeffaf bir şekilde gidiyor" |
| Sorun | Stok %100 doğru değil; güvenliği zayıf ("güvenlik duvarı iyi değil") | - |
| Mimari | Bir **ana sunucu** + terminaller; lokal işleniyor, **gün sonunda ana sunucuya** gidiyor; ana sunucu yoksa diğerleri çalışmıyor | |
| Destek | 7/24 uzaktan bağlantıyla destek | |

- İki sistem **bağımsız**, entegrasyon yok. "Tek sıkıntımız konuşmaması." Daha önce entegrasyon çalışması yapılmış, olmamış.
- "Birini sistem yönetirken diğerini insan yönettiği için" uyumsuzluk yaşanıyor.
- 30 yıllık sistem: konuşmada "30 yılı aşkın Kerzz" gibi geçiyor ama transkript net değil → **teyit edilmeli**.
- Korunması gerekenler: **ciro** raporları, **kasa programı**.
- Sistem ekranlarının fotoğrafı paylaşılabilir ("Var").
- Personel: yeni sistem "zorlayabilir ama alışma süreçleri var"; doğru eğitimle sorun olmaz.

### C. Kullanıcılar ve paydaşlar

- Veriyi **satın alma müdürü** giriyor (siparişleri de o veriyor); en son finansa raporlanıyor (22:00-22:10).
- **Depo sorumlusu** malı teslim alıyor ama **veri girmiyor** (22:18-22:21).
- Talep edenler: barmen, mutfak şefi.
- Cihazlar: mutfak, telefon, ofis (16:59-17:06).

### D. Fonksiyonel gereksinimler

| Özellik | Client'ın sözleri (yaklaşık) | Öncelik |
|---|---|---|
| Cari ve kasa | "İlk isteyeceğim kesinlikle cari ve kasa programı… çok doğru ilerlemesi gerekiyor"; "cari hareket kayıtları, kasa kayıtları" | **Must** |
| Fatura / irsaliye girişi | "Faturalar doğru düzgün girilmesi için… vazgeçilmez" | **Must** |
| Fatura PDF'ini otomatik işleme | "PDF şeklinde içine attık, direkt işleyebiliyorsa" | **Must** (insan doğrulamalı) |
| Stok | "fatura, irsaliye, stok bölümü" | **Must** |
| Kritik stok uyarısı | "50'nin altına düştü… uyarı şeklinde" | **Should** |
| Satıştan otomatik stok düşme | "Her ödeme yapıldığında adisyonla entegre çalışması ve stoktan düşürülmesi" | **Should** (KerzzPOS verisine bağlı) |
| Maliyet verisi | "Maliyet için de bir entegrasyon şartı lazım" | **Should** |
| Şubeler arası transfer | "Başka restoranda istenebilir, diğerine götürülebilir, o sistem üzerinden takip ederiz" | **Should** |
| Aylık kârlılık raporu | "Finansta aylık raporlama, kârlılık vesaire" | **Should** |
| Tedarikçiye otomatik sipariş mesajı | "Elektronik ortamda isterim… düştüğünde direkt bir mesaj" | **Could** |
| Kerzz + Netsis tek sistem | "Tek sistemde olsa… vav bir şey olur" (hayal) | **Won't** (kapsam dışı; hoca da daraltmamızı istedi) |
| Kamera ile stok takibi | Ekip önerdi, client "olabilir" dedi | **Won't** (bu dönem) |
| Yapay zekâ ajanları (sipariş, depo) | Ekip önerdi | **Won't** (bu dönem) |

- Günlük rapor: kasa, kredi kartı, girişler-çıkışlar. Bunlar şu an Kerzz'de var (14:17-14:36).
- **Şubeler arası transfer:** 11:05'te "yok" gibi, 24:12'de "evet" deniyor. Transkript belirsiz, **teyit edilmeli**.

### E. Fonksiyonel olmayan gereksinimler

- Cihaz: mutfak, telefon, ofis PC.
- Güvenlik: client mevcut POS'un güvenliğini zayıf buluyor ve bunu açıkça önemsiyor.
- Gıda güvenliği: Tarım ve Orman Bakanlığı denetimleri var; SKT, soğuk zincir, alkol ruhsatı gibi kayıtlar olabilir. Ürünler alınırken sertifikalarına bakılıyor. Stok uzun tutulmadığı için SKT takibi kritik değil.

### F. Kısıtlar ve riskler

- Daha önce **Mobrez** denenmiş (Enzo adlı İtalyan restoranında), kısa süre; "Kerzz kadar verimli değil, raporlar yok gibi", sadece adisyon için basit bir sistem.
- Mevcut POS: ilk kurulum ücreti + aylık bakım ücreti, dolar bazlı. Ödeme gecikirse sistem kapatılıyor. *(Tutar repoda tutulmuyor.)*
- En büyük risk: **alışma süreci, 15 gün - 1 ay**; "oturmuş bir düzen var… atlatabilmek kolay değil." Başka risk görmüyor.

### G. Başarı kriterleri ve MVP

- MVP = **cari ve kasa + fatura/irsaliye + stok** (24:30-25:09).
- Sayımı aylık 4-5 saatten **haftalık**a indirmek "süper olur".

### H. Kapanış

- Örnek belge: menü veya normal bir doküman paylaşılabilir; görüşmeden sonra iletilecek.
- Ekran fotoğrafları paylaşılabilir.

---

## Stok dışında öne çıkan ihtiyaçlar

- Cari ve kasa, stoktan **daha öncelikli**.
- Aylık kârlılık raporlaması.

## Açık sorular

1. 30 yıllık sistem hangisi: KerzzPOS mu, Netsis mi?
2. Şubeler arası malzeme transferi yapılıyor mu? (Kayıtta çelişkili.)
3. KerzzPOS'tan satış verisi nasıl alınabiliyor? (Şu an Excel'e çekiliyor: hangi rapor, hangi format?)
4. Netsis'e fatura "portal üzerinden" nasıl giriyor? e-Fatura XML'leri alınabiliyor mu?
5. Reçete var mı? Bir yemek/kokteyl stokta hangi malzemeyi ne kadar düşürüyor?
6. Şube müdürü rolü var mı? Muhasebeci şirket içi mi?
7. Gıda denetimi için tutulması gereken kayıtlar tam olarak neler?
8. Başarı ölçütleri: fatura başına harcanan süre, servis sırasında biten ürün sayısı.
