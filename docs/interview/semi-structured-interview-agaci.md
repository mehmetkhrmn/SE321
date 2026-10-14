# Semi-Structured Client Interview: Soru Ağacı (Restoran / Stok Takibi)

SE321 yazılım tasarımı projesi için client olan **restoran** ile yapılacak gereksinim toplama görüşmesi. Varsayılan proje fikri: **stok (envanter) takip sistemi**. Sorular, client stoktan başka bir ihtiyacı (sipariş, masa, personel vb.) öne çıkarırsa onu da yakalayacak şekilde açık bırakıldı.

**Ağacın okunuşu:** `Q` ana soru (her görüşmede sorulur), `├─ F` follow-up (cevaba göre sorulur), `└─ P` probe (detay ya da örnek istemek için). `⚑` işaretli dallar, client o konuyu açarsa derinleştirilir; açmazsa geçilebilir.

---

## 1. Hazırlık (görüşmeden önce)

- Restoranın türünü öğrenin (fast food, a la carte, kafe, zincir/tek şube). Menüsüne göz atın: menüdeki ürünler stokta hangi malzemelere dönüşüyor, kabaca fikriniz olsun.
- Görüşmeyi mümkünse **yoğun saatlerin dışında** (ör. 15:00-17:00) ve **restoranda** yapın; depo, mutfak ve kasayı görmek çok şey anlatır.
- Roller: **1 kişi soru sorar**, **1 kişi not alır**, (varsa) **1 kişi** süreyi ve atlanan dalları takip eder.
- Kayıt için **izin alın**.
- Süre hedefi: **45 dakika - 1 saat** (mevcut sistemler dalıyla birlikte ~1 saat).
- Mümkünse sahip/müdür dışında **aşçıbaşı veya depodan sorumlu kişi** ile de 10 dakika konuşmayı rica edin; stoğu fiilen yöneten genelde odur.

---

## 2. Soru Ağacı

```
INTERVIEW
│
├── A. AÇILIŞ VE TANIŞMA (~5 dk)
│   ├── Q1  Kendinizi ve restorandaki rolünüzü anlatır mısınız?
│   │   ├─ F  Restoran ne tür bir işletme? Kaç şube, kaç personel, günde kaç müşteri?
│   │   └─ P  Mutfakta ve depoda kimler çalışıyor, kim neden sorumlu?
│   └── Q2  Stok veya malzeme yönetimiyle ilgili sizi en çok uğraştıran ne?
│       ├─ F  Bir yazılımın bunu çözebileceğini neden düşündünüz? / Daha önce düşündünüz mü?
│       └─ P  Bu sorun çözülmezse önümüzdeki bir yılda ne olur?
│
├── B. MEVCUT STOK SÜRECİ (~12 dk)
│   ├── Q3  Malzeme restorana gelince ne oluyor? Teslim alımdan depoya kadar anlatır mısınız?
│   │   ├─ F  Gelen malı kim kontrol ediyor? Fatura/irsaliye ile karşılaştırılıyor mu?
│   │   │   └─ P  Eksik veya bozuk mal gelince ne yapıyorsunuz?
│   │   └─ F  Malzemeler nerede saklanıyor? (kuru depo, soğuk oda, dondurucu, bar)
│   ├── Q4  Şu an stoğu nasıl takip ediyorsunuz?
│   │   ├─ F  Kağıt, Excel, POS/adisyon programı, yoksa gözle mi?
│   │   │   └─ P  O dosyayı/defteri görebilir miyiz? Kim, ne sıklıkla güncelliyor?
│   │   ├─ F  Sayım ne sıklıkla yapılıyor? (günlük, haftalık, ay sonu)
│   │   │   └─ P  Son sayımı adım adım anlatır mısınız? Ne kadar sürdü?
│   │   └─ P  Sayımla kayıt tutmayınca ne yapıyorsunuz?
│   ├── Q5  Sipariş (satın alma) kararını nasıl veriyorsunuz?
│   │   ├─ F  "Bu malzeme bitti/azaldı" bilgisi kime, nasıl ulaşıyor?
│   │   ├─ F  Kaç tedarikçiyle çalışıyorsunuz? Sipariş nasıl veriliyor? (telefon, WhatsApp, sistem)
│   │   │   └─ P  Bir malzemeyi birden fazla tedarikçiden alıyor musunuz? Fiyat karşılaştırıyor musunuz?
│   │   └─ P  En son bir malzeme servis sırasında bittiğinde ne oldu?
│   ├── Q6  Malzemeler stoktan nasıl düşüyor?
│   │   ├─ F  Satılan bir yemeğin hangi malzemeden ne kadar harcadığını biliyor musunuz? (reçete)
│   │   │   └─ P  Reçeteler yazılı mı? Porsiyonlar standart mı?
│   │   └─ F  Personel yemeği, ikram, mutfak içi kullanım nasıl kaydediliyor?
│   └── Q7  Fire (israf), bozulma ve son kullanma tarihi nasıl yönetiliyor?
│       ├─ F  Ayda ne kadar malzeme çöpe gidiyor? En çok hangileri?
│       ├─ P  Son kullanma tarihi yaklaşan ürünü nasıl fark ediyorsunuz? (FIFO uygulanıyor mu?)
│       └─ ⚑ P  Kayıp veya kaçak şüphesi yaşadınız mı? Nasıl anladınız?
│
├── B+. MEVCUT SİSTEMLER (~10 dk) ★ Ön bilgi: restoran şu an 2 sistem kullanıyor, biri ~30 yıllık
│   ├── S1  Şu an kullandığınız iki sistemi anlatır mısınız? Her biri ne işe yarıyor?
│   │   ├─ F  Adları ne? Hangisi 30 yıllık? Diğeri ne zamandır kullanılıyor?
│   │   ├─ F  Hangi işler hangi sistemde yapılıyor? (stok, adisyon/satış, muhasebe, fatura, personel)
│   │   └─ P  Ekranlarını kısaca gösterebilir misiniz? Bir günlük kullanımı birlikte izleyebilir miyiz?
│   ├── S2  İki sistem birbiriyle konuşuyor mu?
│   │   ├─ F  Aynı bilgiyi iki sisteme ayrı ayrı girdiğiniz oluyor mu? (çift giriş)
│   │   │   └─ P  En son ne zaman iki sistemdeki rakamlar birbirini tutmadı? Ne yaptınız?
│   │   └─ P  Sistemler arasında veriyi elle mi taşıyorsunuz? (Excel, kağıt, yeniden yazma)
│   ├── S3  30 yıllık sistemde en çok neyi seviyorsunuz? Neden hâlâ kullanıyorsunuz?
│   │   ├─ F  Yeni sistemde mutlaka korunması gereken bir alışkanlık/özellik var mı? (kısayol, ekran, rapor)
│   │   └─ P  "Bu olmazsa geçmem" dediğiniz bir şey?
│   ├── S4  O sistemde sizi en çok ne zorluyor?
│   │   ├─ F  Arıza, yavaşlık, yedekleme, donanım (eski PC, yazıcı), destek veren kimse kalmadı mı?
│   │   └─ P  Bozulursa ne olur? Daha önce bozulduğunda ne yaptınız?
│   ├── S5  Eski sistemdeki veriler sizin için ne kadar önemli?
│   │   ├─ F  Geçmiş kayıtlar (malzeme listesi, tedarikçi, reçete, satış) yeni sisteme taşınmalı mı? Ne kadar geriye?
│   │   └─ P  Veriyi dışarı alabiliyor musunuz? (Excel/CSV çıktısı, yazıcı raporu, dosya) Bir örnek alabilir miyiz?
│   ├── S6  İdeal durumda ne olmalı?
│   │   ├─ F  İki sistemin yerine tek sistem mi, yoksa yeni sistem mevcutlarla birlikte mi çalışsın?
│   │   └─ P  Hangisinden vazgeçmeniz daha kolay? Hangisi kesinlikle kalmalı?
│   └── S7  Personel eski sisteme ne kadar alışkın? Yeni bir sisteme geçiş nasıl olmalı?
│       └─ P  Bir süre iki sistem paralel çalışabilir mi? Eğitim için kimin zamanı var?
│
├── C. KULLANICILAR VE PAYDAŞLAR (~6 dk)
│   ├── Q8  Bu sistemi kimler kullanacak?
│   │   ├─ F  Her kişi ne yapacak? (sahip: rapor; müdür: sipariş; aşçı: tüketim; depocu: giriş/sayım)
│   │   │   └─ P  Kimin göremeyeceği / değiştiremeyeceği bilgi olmalı? (maliyet, fiyat)
│   │   ├─ F  Personel bilgisayar/telefonla ne kadar rahat? Personel değişimi sık mı?
│   │   └─ P  Mutfakta, eldivenle, aceleyle kullanılacak mı? Hangi cihazla? (tablet, telefon, PC)
│   └── Q9  Sisteme dokunmayıp sonucundan etkilenen kimler var? (muhasebeci, tedarikçi, ortaklar)
│       └─ P  Son kararı kim verir?
│
├── D. FONKSİYONEL GEREKSİNİMLER (~12 dk)
│   ├── Q10 Sistemin mutlaka yapması gereken işler neler? (önem sırasına koyalım: Must / Should / Could)
│   │   │   Client tıkanırsa örnek olarak sunun:
│   │   │   malzeme kartları, mal kabul/stok girişi, tüketim/çıkış, sayım,
│   │   │   kritik stok uyarısı, sipariş listesi, fire kaydı, tedarikçi listesi, raporlar
│   │   ├─ F  [özellik] derken tam olarak ne kastediyorsunuz? Bir örnekle anlatır mısınız?
│   │   └─ P  Bu özellik olmasa sistemi yine kullanır mıydınız?
│   ├── Q11 Bir malzeme için hangi bilgileri tutmak istersiniz?
│   │   ├─ F  Birimler nasıl? (kg, litre, adet, koli) Birim dönüşümü gerekir mi? (1 koli = 12 adet)
│   │   └─ P  Son kullanma tarihi, parti/lot, depo yeri, alış fiyatı tutulmalı mı?
│   ├── Q12 Stok azaldığında sistemin ne yapmasını beklersiniz?
│   │   ├─ F  Kritik seviyeyi kim belirlesin? Sabit mi, haftanın gününe göre mi değişsin?
│   │   └─ P  Uyarı nasıl gelsin? (ekranda, bildirim, e-posta) Kime?
│   ├── ⚑ Q13 Sistem sipariş önerisi hazırlasın ya da tedarikçiye siparişi kendisi göndersin ister misiniz?
│   ├── Q14 Hangi raporları görmek istersiniz?
│   │   ├─ F  Ör. günlük/haftalık tüketim, fire raporu, maliyet, en çok harcanan malzeme, yemek başı maliyet
│   │   └─ P  Bugün bu rakamları nasıl çıkarıyorsunuz? Ne sıklıkla bakarsınız?
│   ├── ⚑ Q15 POS/adisyon sistemi ile bağlantı gerekiyor mu? (satış oldukça malzeme otomatik düşsün)
│   │   └─ P  Hangi POS'u kullanıyorsunuz? Satış verisini dışarı alabiliyor musunuz?
│   ├── ⚑ Q16 Birden fazla şube veya depo var mı? Şubeler arası transfer oluyor mu?
│   └── Q17 Hayal ettiğiniz ama "çok zor olur" diye söylemediğiniz bir özellik var mı?
│       └─ P  (Barkod okutma, fatura fotoğrafından giriş, talep tahmini gibi)
│
├── E. FONKSİYONEL OLMAYAN GEREKSİNİMLER (~6 dk)
│   ├── Q18 Sisteme nereden ve hangi cihazdan girilecek? (mutfak tableti, telefon, ofis PC)
│   │   └─ P  Depoda/soğuk odada internet çekiyor mu? İnternet giderse ne olmalı?
│   ├── Q19 Bir stok girişi ya da sayım en fazla ne kadar sürmeli ki personel kullansın?
│   │   └─ P  Beğendiğiniz ya da nefret ettiğiniz bir uygulama örneği?
│   ├── Q20 Hangi bilgiler hassas? (alış fiyatları, tedarikçi anlaşmaları, kâr marjı)
│   │   └─ P  Kim neyi değiştirdi, kayıt altında olsun mu? (geçmiş / log)
│   └── ⚑ Q21 Gıda güvenliği veya denetim için tutmanız gereken kayıt var mı? (son kullanma, soğuk zincir)
│
├── F. KISITLAR VE RİSKLER (~5 dk)
│   ├── Q22 Bütçe, zaman veya donanım açısından bir sınır var mı?
│   │   └─ P  Aylık ücretli bir sistemi mi, tek seferlik bir çözümü mü tercih edersiniz?
│   ├── Q23 Daha önce stok programı denediniz mi? Neden bıraktınız? (mevcut 2 sistem S1-S7'de soruldu; burada başka denenip bırakılanlar)
│   └── Q24 Personelin sisteme veri girmemesi riski hakkında ne düşünüyorsunuz?
│       └─ P  Veri girişini kim kontrol edebilir?
│
├── G. BAŞARI KRİTERLERİ (~4 dk)
│   ├── Q25 Sistemi 6 ay kullandıktan sonra "işe yaradı" demeniz için ne değişmiş olmalı?
│   │   ├─ F  Ör. fire %?, servis sırasında biten malzeme sayısı, sayım süresi, malzeme maliyeti
│   │   └─ P  Bu değerler şu an yaklaşık ne kadar?
│   └── Q26 İlk sürümde en azından ne olursa kullanmaya başlarsınız? (MVP)
│
└── H. KAPANIŞ (~5 dk)
    ├── Q27 Sormadığımız ama bilmemiz gereken bir şey var mı?
    ├── Q28 Paylaşabileceğiniz örnek belge var mı? (fatura/irsaliye, sayım listesi, Excel, reçete, menü)
    ├── Q29 Depoyu ve mutfağı kısaca görebilir miyiz?
    ├── Q30 Anladıklarımızı özetleyeyim, eksik/yanlış var mı? (özet + onay)
    └── Q31 Prototipi göstermek için tekrar görüşebilir miyiz? Size nasıl ulaşırız?
```

---

## 3. Semi-Structured Yöntem İçin İpuçları

**Akış**
- Ağaç bir **rehber**, senaryo değil. Client başka bir dala geçerse peşinden gidin; atlanan ana soruları sona doğru toplayın.
- Her bölüme **açık uçlu** bir ana soruyla girin ("Nasıl…", "Anlatır mısınız…"), sonra follow-up ile daraltın.
- **Huni tekniği:** önce mevcut süreci anlatsın (B), sonra özelliklere geçin (D). Özellik listesini (Q10'daki örnekler) client tıkanmadıkça sunmayın; kendi söylediği ihtiyaç daha değerlidir.
- Client "stok" yerine başka bir sorunu (sipariş/adisyon, masa rezervasyonu, personel vardiyası) daha çok vurgularsa not edin; proje kapsamını ekipçe sonra konuşursunuz.

**Derinleştirme (probe) kalıpları**
- "En son ne zaman oldu? Anlatır mısınız?" (ör. "En son ne zaman bir malzeme servis sırasında bitti?")
- "Bunu biraz daha açar mısınız?"
- "Neden bu sizin için önemli?" (5 Neden: gerçek ihtiyaca inene kadar)
- "Bu olmasa ne olurdu?"
- Sessizlik: cevaptan sonra 3-4 saniye bekleyin.

**Mevcut sistemler (legacy) için dikkat edilecekler**
- Restoran zaten 2 sistem kullanıyor, biri ~30 yıllık. Bu yüzden B+ dalı **önceliklidir**; süre kısıtlıysa D'deki ⚑ dallardan kısın.
- 30 yıllık sistemi eleştirmeyin; personel ona alışkın ve sevdiği yanları olabilir. "Neden hâlâ kullanıyorsunuz?" sorusu gerçek gereksinimi verir.
- Proje kapsamı netleşmeli: **yerine geçmek** mi (veri taşıma, eğitim), **yanında çalışmak** mı (entegrasyon, çift giriş riski), yoksa **sadece eksik kalan işi** (ör. stok) mi çözmek?
- Mümkünse iki sistemden örnek ekran görüntüsü ve dışa aktarılmış veri isteyin; tasarımda veri modeli ve geçiş planı için gerekecek.

**Restorana özel dikkat edilecekler**
- **Birim karmaşası** (koli/kg/porsiyon) ve **reçete** stok sistemlerinin en zor kısmıdır; Q6 ve Q11'de mutlaka somut örnek isteyin (ör. "Bir hamburger için hangi malzemeden ne kadar gidiyor?").
- Stoğu sahip değil, mutfak/depo personeli girecek. "Bunu yoğun bir cumartesi akşamı kim, ne zaman girecek?" sorusu gerçekçi gereksinim çıkarır.
- Fire ve kayıp konuları hassas olabilir; suçlayıcı değil merak eden bir tonla sorun.

**Kaçınılacaklar**
- Yönlendirici sorular: ~~"Barkodlu sistem olsa iyi olmaz mı?"~~ yerine "Malzemeyi sisteme girmenin en kolay yolu sizce ne olur?"
- Teknik jargon (veritabanı, API, framework).
- Görüşmede söz vermek ("Onu kesin yaparız").
- Aynı anda iki soru sormak.

**Not alma**
- Client'ın **kendi cümlelerini** tırnak içinde yazın.
- Notları üç etikete ayırın: **ihtiyaç**, **sorun (pain point)**, **kısıt**.
- Belirsizleri "açık soru" listesine yazın.

**Görüşmeden sonra (aynı gün)**
1. Notları ekipçe birleştirin.
2. Gereksinimleri fonksiyonel / fonksiyonel olmayan olarak listeleyin, MoSCoW önceliği verin.
3. **User story** ("Bir depo sorumlusu olarak, kritik seviyenin altına düşen malzemeleri görmek istiyorum, böylece zamanında sipariş verebilirim") ve **use case** taslakları çıkarın (ör. Mal Kabul, Stok Sayımı, Fire Kaydı, Sipariş Oluşturma).
4. Kısa bir özet e-postasıyla client'tan onay alın.

---

## 4. Görüşmede Doldurulacak Kısa Not Şablonu

| Bölüm | Önemli cevaplar (client'ın sözleri) | Pain point | Gereksinim | Açık soru |
|---|---|---|---|---|
| B. Mevcut stok süreci | | | | |
| B+. Mevcut sistemler | | | | |
| C. Kullanıcılar | | | | |
| D. Fonksiyonel | | | | |
| E. Fonks. olmayan | | | | |
| F. Kısıtlar | | | | |
| G. Başarı | | | | |
