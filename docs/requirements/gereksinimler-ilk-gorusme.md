# Gereksinimler: 15.10.2026 Client Görüşmesi

**Kaynak:** 15.10.2026 tarihli client görüşmesinin ses kaydı (~25:38). Görüşülen kişi: Mustafa Ulukaya, Financial Director, Rise Group.

**Yöntem ve sınırlar**
- Bu listede sadece görüşmede **açıkça söylenen, ima edilen veya tartışılan** gereksinimler var. Proposal'da olup kayıtta geçmeyen maddeler (ör. faturalarda insan onayı, rol bazlı yetki, audit log) buraya **alınmadı**. Bunlar hocanın feedback'inden geliyor; listesi en altta.
- Alıntılar ses kaydının **otomatik transkriptinden** birebir alındı. Transkriptte kelime hataları olabilir; anlaşılmayan yerler `[…]` ile kısaltıldı. Köşeli parantez içindeki notlar bize ait.
- Transkriptte konuşmacı ayrımı yok. **Konuşmacı bağlamdan çıkarıldı:** "Client" = Mustafa Ulukaya, "Ekip" = proje grubu.
- Zaman damgası biçimi `[dd:ss]`, kaydın başından itibaren.

---

## Client'ın Öncelik Sırası

Client "ilk isteyeceğiniz 3 şey" sorusuna şöyle cevap verdi: **(1) cari ve kasa, (2) fatura/irsaliye, (3) stok.**

**Kaynak/Zaman Damgası:**
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..." `[24:42]`: "Çok doğru bir şekilde ilerlemesi gerekiyor."
- Client, `[24:56]`: "...fatura biriminde, faturalar da doğru düzgüne girilmesi için." `[24:59]`: "Onlar vazgeçilmez şeyler."
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..." `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."

---

## 1. Fonksiyonel Gereksinimler

### 1.1 Cari ve Kasa

**FR-01: Cari hesap hareketleri**
- Sistem cari hesap hareketlerini kaydetmeli ve takip etmelidir.

Kaynak/Zaman Damgası:
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..."
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..."
- Client, `[03:45]`: "Netsis burada fatura, cari dökümü vesaire." [Bugün cari dökümü Netsis'te tutuluyor.]

**FR-02: Kasa kayıtları**
- Sistem kasa kayıtlarını (nakit, kredi kartı, girişler ve çıkışlar) tutmalıdır.
- Mevcut "kasa programı" işlevi yeni sistemde korunmalıdır.

Kaynak/Zaman Damgası:
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..."
- Client, `[09:36]`: "Cirolar, cirolar, cirolar." `[09:38]`: "Tabi ki kasaprogramın özellikle." [Ekibin `[09:20]`'deki "korunması gereken özellik" sorusuna cevap.]
- Client, `[14:30]`: "Özellikle kasanın akit, kredi kartı, girişler çıkışlar."

**FR-03: Raporlama (ciro, gün sonu kasa, aylık kârlılık)**
- Sistem gün sonu kasa raporu üretmelidir: nakit, kredi kartı, girişler ve çıkışlar.
- Sistem ciro raporları üretmelidir.
- Raporlama en az mevcut KerzzPOS'taki kadar ayrıntılı olmalıdır.
- Sistem finans için aylık raporlama yapabilmelidir (kârlılık vb.).

Kaynak/Zaman Damgası:
- Ekip, `[14:17]`: "Her gün sonu görmek istediğiniz bir rapor vesaire oluyor mu?" Client, `[14:27]`: "Var zaten." `[14:30]`: "Özellikle kasanın akit, kredi kartı, girişler çıkışlar."
- Client, `[09:36]`: "Cirolar, cirolar, cirolar."
- Client, `[07:36]`: "Ya da mesela Kerzz'de raporlama kısmında" `[07:39]`: "daha ayrıntılı bir ton istediğinin" `[07:41]`: "her raporu veriyor yani."
- Client, `[13:09]`: "Yani Kerzz kadar aktif değil, verimli değil dediği gibi raporlar vs. hiç yok gibi bir şey." [Daha önce denenip bırakılan Mobrez için.]
- Client, `[16:01]`: "Hem finansda raporlama, aylık raporlama dediğimiz var bizim karlılık vesaire de."

### 1.2 Fatura ve İrsaliye

**FR-04: PDF fatura yükleme ve otomatik işleme**
- Kullanıcı gelen tedarikçi faturasını PDF olarak sisteme yükleyebilmelidir.
- Sistem PDF faturanın içeriğini otomatik olarak işleyip kaydetmelidir (client'ın ifadesiyle "yapay zekâ tarzı").

Kaynak/Zaman Damgası:
- Client, `[01:13]`: "Şimdi bizim en büyük problemimiz, fatura geldiğinde o faturayı isteme işlemek bizim için çok büyük bir problem."
- Client, `[01:25]`: "O süreçte böyle yapay zekalindeki hastanın tarzını da mesela atıyorum." `[01:29]`: "Fatura geldi, pdf şeklinde içine attık." `[01:32]`: "O direk Netsis'e ya da herhangi bir yere işleyebiliyorsa, mesela öyle bir sistem olur."
- Client, `[24:56]`: "...faturalar da doğru düzgüne girilmesi için." `[24:59]`: "Onlar vazgeçilmez şeyler."

**FR-05: Fatura kalemlerinde birim tutar ve değişken iskonto**
- Fatura girişinde her kalem için birim tutar ve iskonto kaydedilebilmelidir.
- İskonto faturadan faturaya farklı olabilir; sistem sabit iskonto varsaymamalıdır.

Kaynak/Zaman Damgası:
- Client (bağlamdan), `[19:22]`: "Her zaman böyle birim tutarına giriyorsun." `[19:24]`: "Biraz daha mesela yanlar hatununda iskonto kısmı var." `[19:28]`: "İskonto kısmına giriyorsun." `[19:29]`: "Her zaman aynı iskonto öyle gelmedi." `[19:32]`: "Fatur'a direk entegre ettiğin zaman aslında onu da..."

**FR-06: İrsaliye kaydı**
- Sistem tedarikçiden gelen irsaliyeleri kaydetmelidir.

Kaynak/Zaman Damgası:
- Client, `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."
- Client, `[05:01]`: "Aynı şekilde mal geldiğine dair bir WhatsApp üzerinde bilgi veriyor." `[05:08]`: "İrsaliye ve fotoğra da gördüğümüz için o şekilde biz de teyit ediyoruz." [Bugün irsaliye teyidi WhatsApp'taki fotoğrafla yapılıyor.]

### 1.3 Stok

**FR-07: Satışta otomatik stok düşümü (adisyon entegrasyonu)**
- Sistem stok takibi yapmalıdır.
- Her ödeme yapıldığında sistem adisyonla (masa fişi, ürünler) entegre çalışmalı ve satılan ürünler stoktan otomatik düşülmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[14:39]`: "Peki yeni oluşturulacak sistemin POS yazılımınıza yani daha doğrusu adisyon sisteminizi entegri olmasını ister misiniz?"
- Client, `[14:48]`: "Neticede bir adisyon fişi belledir her masanın." `[14:52]`: "Ürün, istenen ürün belledir." `[14:55]`: "Her ödeme yapıldığında POS yazılımının adisyonu entegre çalışması ve arkada stock systemleri rejimli olup, stock'tan düşürülmesi."
- Client, `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."

**FR-08: Birim dönüşümü (koli → şişe/adet)**
- Sistem ürünleri koli olarak alıp stokta adet/şişe olarak tutabilmeli; koli içindeki adet sayısıyla otomatik dönüşüm yapmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[07:44]`: "Siz bir de hani içecekleri stokta tutarken" `[07:48]`: "şey kolyo kolyo olarak mı tutuyorsunuz?" `[07:51]`: "Yoksa şişe o sayısını mı biliyorsunuz direkt?"
- Client, `[07:58]`: "Yani bir kolyo geliyor çarpıyoruz."
- Client, `[04:23]`: "İki koli, Chivas 18 geldi."

**FR-09: Kritik stok uyarısı**
- Bir ürünün stoğu belirlenen seviyenin altına düştüğünde sistem kullanıcıya uyarı vermelidir (ör. soft içecek 50 adedin altına düştüğünde).

Kaynak/Zaman Damgası:
- Client, `[03:09]`: "Mesela Kerzz'de atıyorum." `[03:10]`: "Ürün bittiğinde bize bildirim tarzına bir şey gelmiyor." `[03:12]`: "Atıyorum mesela soft içecekler de." `[03:14]`: "50'nin altına düştü mesela." `[03:16]`: "Bize böyle bir uyarı şeklinde," `[03:18]`: "gelebilirsiniz diye bir şey olursa mesela."

**FR-10: Stok azaldığında tedarikçiye otomatik mesaj**
- Stok azaldığında sistem tedarikçiye elektronik ortamda otomatik bir sipariş/bildirim mesajı gönderebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[12:09]`: "Diyelim ki stoğumuz azalmaya başladı." `[12:13]`: "Siz tedarikçinize otomatik olarak bildirmesini ister misiniz?"
- Client, `[12:23]`: "Üstelik ortamda isterim." `[12:26]`: "Çünkü elektronik düştüğümde direk bir mesaj olacak." ["Elektronik ortamda isterim" olarak anlaşılıyor.]

**FR-11: Stok sayımı**
- Sistem şube bazında stok sayımı yapılmasını desteklemelidir.
- Sayım haftalık yapılabilecek kadar kolay olmalıdır (süre hedefi: NFR-05).

Kaynak/Zaman Damgası:
- Client, `[17:20]`: "Ortalama bir iki kişi oluyor." `[17:25]`: "Yaklaşık 4-5 saat sürüyor." `[17:31]`: "Aylık oluyor."
- Client, `[17:36]`: "Mesela bu sistemle haftalık olsa süper olur." `[17:39]`: "Evet, haftalık sayıda."

**FR-12: Şubeler arası malzeme transferi** ⚠️ *Kayıtta çelişkili, teyit edilmeli*
- Sistem bir şubeden diğerine yapılan malzeme transferini kaydedip takip edebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[24:12]`: "Bunların arasında malzemelaş verişi yapıyorsunuz galiba." `[24:17]`: "Yapıyor musunuz?" Client, `[24:18]`: "Evet."
- Ekip, `[24:20]`: "Yani hepsi entegre olabilir bir sistem altında." `[24:23]`: "Başka bir restoranları istenebilir." `[24:25]`: "Diğerine götürülebilir." `[24:27]`: "O sistem üzerinden takip ederiz." Client, `[24:29]`: "Evet."
- **Çelişki:** Ekip, `[11:05]`: "Sizin farklı şubeler arasında malzeme transferi vesaire oluyor mu?" Client, `[11:14]`: "Yok şey malzeme içi normal."

**FR-13: Maliyet verisi entegrasyonu** *(client: "olursa iyi olur")*
- Sistem maliyet verilerini doğrudan alabilecek şekilde entegre çalışmalıdır.

Kaynak/Zaman Damgası:
- Client, `[15:06]`: "Aynı zamanda maliyet için de bir entegrasyon şartı lazım." `[15:09]`: "Direkt maliyetin verileri alabildiği bir entegrasyon sistemi yaptılar." `[15:14]`: "Yani o da oluşta iyi olur." [= olursa iyi olur]

### 1.4 Sistemler Arası Veri Akışı

**FR-14: Çift veri girişini ve elle aktarımı ortadan kaldırma**
- Satış (POS), alış faturası ve muhasebe (Netsis) verileri birbiriyle konuşmalıdır. Excel üzerinden elle aktarım ve aynı verinin iki sisteme ayrı ayrı girilmesi ortadan kalkmalıdır.
- İşlenen fatura verisi Netsis'e (veya ilgili yere) aktarılabilmelidir.

Kaynak/Zaman Damgası:
- Client, `[01:45]`: "Yani KerzzPOS kullanıyoruz. Ayrıca muhasebe programı olarak Netsis programı kullanıyoruz." `[01:55]`: "Açısından birbirlerine konuşmalar." `[02:02]`: "İki iş oluyor."
- Client, `[02:15]`: "Elektronik ortama Excel yönünden aktarıyor." `[02:18]`: "KerzzPOS sisteminden satışlar çekiliyor." `[02:22]`: "Alınan alış faturaları giriliyor." `[02:25]`: "Ama tabii ki bu dediğim gibi tekrardan Netsis'e işlenmiyor."
- Ekip, `[05:48]`: "İkisi senin birbiriyle entegrasyonu var mı?" Client, `[05:53]`: "Bağımsı kullanıyoruz."
- Client, `[08:39]`: "Dediğim gibi tek sıkıntımız konuşmaması." `[08:42]`: "İntegrasyonu asla yok." `[08:51]`: "Excel'e dökülüyor sayınlar vesaire." `[08:53]`: "Ama Netsis'te girişi olmuyor."
- Client, `[01:32]`: "O direk Netsis'e ya da herhangi bir yere işleyebiliyorsa, mesela öyle bir sistem olur."
- Client, `[15:54]`: "Hem Netsis ya da Kerzz ile Netsis." `[15:57]`: "Tek sistemde olsa hem arkadaşlarımız için çok rahat olur." `[16:07]`: "Çok rahat ve çok muhteşem, vav bir şey olur bizim için."

---

## 2. Non-Fonksiyonel Gereksinimler

**NFR-01: Güvenlik**
- Client mevcut KerzzPOS'un güvenlik duvarını yetersiz buluyor. Yeni sistemin güvenlik altyapısı mevcut sistemden daha güçlü olmalı ve dış saldırılara karşı korumalı olmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[09:42]`: "Peki en major probleminiz nedir bu sistemdeki, eski sistemdeki ve en büyük probleminiz nedir?"
- Client, `[10:10]`: "[…] Bir güvenlik duvarı oluşmunda mesela en büyük problemleri o. Bence güvenlik" `[10:15]`: "duvara hala söylüyorum. Yıllı 2026'i KerzzPOS'un güvenlik duvarı iyi bir donanın değil." `[10:20]`: "Değil. Net olarak söyleyebiliyorum."
- *Not: Client bu bölümde geçmişte yaşanan bir güvenlik olayından da bahsediyor (`[10:02]`). Repo public olduğu için ayrıntısı buraya alınmadı.*

**NFR-02: Hassas verilerin korunması** ⚠️ *Ekip sordu; client'ın teyidi net değil*
- Alış fiyatları, tedarikçi anlaşmaları ve kâr marjları hassas bilgi olarak korunmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[19:01]`: "Tutmandığınız sistemdeki biraz da hassas olan bilgiler." `[19:10]`: "Alışfiyatlarınız olabilir çünkü tedarikçi ile anlaşıyorsunuz." `[19:13]`: "Tedarikçi ile anlaşmaları yine dediğim gibi veya kar marjları satılıyorum da." `[19:17]`: "Soft içeceğin size gelişi farklıdır." `[19:19]`: "Satış fiyatı farklıdır."
- *Client'ın cevabı (`[19:22]`–`[19:32]`) iskonto konusuna geçiyor; erişim kısıtlaması açıkça istenmedi.*

**NFR-03: Veri doğruluğu**
- Cari, kasa, fatura ve stok kayıtları doğru tutulmalıdır. Mevcut KerzzPOS'taki "%100 doğru olmayan" stok sorunu yeni sistemde olmamalıdır.

Kaynak/Zaman Damgası:
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..." `[24:42]`: "Çok doğru bir şekilde ilerlemesi gerekiyor."
- Client, `[24:56]`: "...faturalar da doğru düzgüne girilmesi için."
- Client, `[03:35]`: "Tabii ki, KerzzPOS dediğim gibi." `[03:37]`: "Orada stok ve yüzde yüz verilerle ilerlemiyor."
- Client, `[06:15]`: "Orada yani yüzde yüz verilerle takip edilmiyor tabii ki."
- Client, `[08:19]`: "Ya zaten veriler birbirlerine uyumuyor."

**NFR-04: Kapasite (fatura hacmi ve sezonluk yoğunluk)**
- Sistem yoğun sezonda haftada 70-80 tedarikçi faturasını işleyebilmelidir.
- Yazın şubeler açıldığında fatura sayısındaki ani artışı karşılayabilmelidir. Mal girişleri haftada iki gün, iş en çok hafta sonu yoğunlaşıyor.

Kaynak/Zaman Damgası:
- Client, `[01:19]`: "Çünkü yazın, dükkanı açılıyor, birden bir fatura yılın oluyor mesela."
- Client, `[18:21]`: "Genelde haftalık iki gün, bizim özellikle hafta sonu çok iş oluyor."
- Client, `[18:33]`: "Bu hafta gelen faturası ise 76 […]" `[18:38]`: "İşte 76'da ne var diyeceksin alkolü, soft içeceği, çerezi, işte gıda malzemeleri, tedarikçi firmalar gibi gibi." `[18:46]`: "Yani 70'de 80'in fotoğruğu geliyor." `[18:56]`: "Bu haftalık."

**NFR-05: Sayım süresi (performans / kullanılabilirlik)**
- Stok sayımı bugünkü 4-5 saatten (aylık, 1-2 kişi) kısa sürmeli ve haftalık yapılabilir olmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[17:09]`: "Bir stock girişi ya da sayımı en fazla ne kadar sürmeli ki personel kullanabilirsin?"
- Client, `[17:20]`: "Ortalama bir iki kişi oluyor." `[17:25]`: "Yaklaşık 4-5 saat sürüyor." `[17:31]`: "Aylık oluyor."
- Client, `[17:36]`: "Mesela bu sistemle haftalık olsa süper olur." Ekip, `[17:40]`: "Yani ne hızlı olabilirse bu sistem bir haftaya kadar indirebilir o zaman." Client, `[17:44]`: "Kesinlikle."

**NFR-06: Çok şubeli ve sezonluk yapı**
- Sistem birden fazla işletmeyi desteklemelidir: yazın 4-5, kışın 3 işletme, yılda toplam yaklaşık 250 personel.

Kaynak/Zaman Damgası:
- Ekip, `[00:24]`: "Toplamda kaç şube, kaç personel?"
- Client, `[00:26]`: "Yaklaşık, yazın aktif olarak 4-5, kışında 3 işletme var." `[00:36]`: "Toplam yıl içerisinde yaklaşık 250 personeli buluyor."

**NFR-07: Cihaz ve erişim**
- Sisteme mutfaktan, telefondan ve ofisten erişilebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[16:59]`: "Sistemenlerden ve hangi cihazdan girecek?"
- Client, `[17:04]`: "Mutfakta vereceğimize." `[17:05]`: "Telefon, ofis..."

**NFR-08: Öğrenilebilirlik ve geçiş süreci**
- Mevcut sisteme alışkın personel, doğru eğitimle yeni sisteme geçebilmelidir. Client'ın beklediği alışma süresi 15 gün ile 1 ay arası.

Kaynak/Zaman Damgası:
- Ekip, `[11:28]`: "Yıllardır sizinle beraber çalışan çalışanlar nezilde eski sisteme ne kadar hakimler ne kadar alışkınlar?" `[11:34]`: "Yeni bir sisteme geçiş var olan eski çalışanlarınızı zorlar mı?"
- Client, `[11:38]`: "Zorlayabilirim ketapta ama alışma süreçleri var." `[11:43]`: "Doğru eğitimini verildiği senaryoda süreç uzaması."
- Client, `[23:03]`: "Aslında risk tabi de bununla alışma süreci var." `[23:07]`: "Yani bu alışma süreci de biraz zaman alabilir." `[23:10]`: "On beş gün bir ay kadar." `[23:18]`: "Çünkü bağır olan bir düzen var." `[23:22]`: "Bunu atlatabilmek kolay değil tabii ki."

**NFR-09: Destek ve süreklilik**
- Sorunlara 7/24 uzaktan destekle müdahale edilebilmelidir. Client bunu mevcut sistemin işe yarayan bir yanı olarak anlattı.
- Ödeme gecikmesi gibi ticari bir sebeple sistem hemen kapatılmamalıdır. Client mevcut sağlayıcının bu uygulamasından şikâyetçi.

Kaynak/Zaman Damgası:
- Client, `[13:56]`: "Şimdi şöyle 7-20'lü uzaktan bağlantıyla hizmet veriyorlar." `[14:00]`: "Yani bu hafta sonunda olsa, gece 5'de olsa, 3'de olsa bir hizmet olduğu için uzaktan hemen […]" `[14:10]`: "Genelde çoğu zaman hallediyor yani problem."
- Client, `[21:36]`: "İkince vesaire direkt mesel sistem kapanıyor." `[21:41]`: "Ücreti alamadınız ama mesela direkt hemen sistemi kapatıyor." `[21:51]`: "Memleketimin insanı yapsaydı böyle olmuyor." `[21:53]`: "Parayı faizle düşürürdü ama yine sistem çalışır oluyor."
- *Not: Client'ın ödediği ve kabul edebileceği aylık ücret tutarı (`[13:47]`, `[21:10]`–`[21:16]`) kayıtta geçiyor; repo public olduğu için buraya alınmadı.*

---

## 3. Tartışılan Ama Gereksinim Olarak Alınmayanlar

| Konu | Neden alınmadı | Kaynak/Zaman Damgası |
|---|---|---|
| Fire, bozulma ve SKT'nin elektronik takibi | Bugün manuel; client bunu istemedi. Ürünler "bozulacak kadar durmuyor". | Client, `[03:26]`: "Yok, manuel."; `[20:23]`: "Bozulacak kadar durmuyor zaten." |
| Gıda denetimi kayıtları (SKT, soğuk zincir, alkol ruhsatı) | Client "muhtemelen vardır" dedi; ne tutulacağı belirsiz. **Açık soru.** | Client, `[19:48]`: "Muhtemelen vardır." `[19:50]`–`[19:55]`; `[20:15]`: "Zaten ürünleri alırken seykatelerine bakıyorlar." [= sertifikalarına] |
| Yapay zekâ ajanları (stok, sipariş, depo) | Ekibin fikri; client istemedi. | Ekip, `[16:36]`–`[16:45]` |
| Kamera ile stok takibi | Ekip önerdi; client sadece "Olabilir" dedi. | Ekip, `[17:45]`–`[18:09]`; Client, `[18:10]`: "Olabilir." |
| Yedekleme | Ekip örnek olarak saydı; client açık bir talepte bulunmadı. | Ekip/Client, `[09:48]`–`[09:57]` |

## 4. Mevcut Süreçten Çıkan Bilgiler (aktör ve iş akışı için)

Bunlar gereksinim değil, bugünkü işleyişin tarifi. Use case ve aktörleri tanımlarken kullanılacak.

- **Roller:** mutfak şefi, satın alma müdürü, depo sorumlusu, komi, garson, barboy, barmen. Client `[00:47]`–`[00:57]`, `[02:56]`–`[03:04]`.
- **Talep ve onay:** Barmen ve şef taleplerini WhatsApp grubuna yazıyor, satın alma onaylıyor; planlama haftalık. Client `[02:46]`–`[03:07]`.
- **Mal kabul:** Depo sorumlusu malı kapıda teslim alıyor, iki taraf da kaşe-imza atıyor, mal bara ya da -2. kattaki depoya gidiyor, irsaliye fotoğrafı WhatsApp'a atılıyor. Client `[04:11]`–`[05:08]`.
- **Bozuk mal:** İade süreci başlıyor. Client `[05:35]`–`[05:41]`.
- **Veri girişi:** Veriyi satın alma müdürü giriyor, depo sorumlusu veri girmiyor. Client `[22:02]`–`[22:21]`.
- **Mevcut KerzzPOS mimarisi:** ana sunucu ve terminaller; veri lokal işleniyor, gün sonunda ana sunucuya gidiyor. Client `[10:42]`–`[10:53]`.

## 5. Kayıtta Olmayan, Proposal'dan / Hoca Feedback'inden Gelen Maddeler

Aşağıdakiler bu listeye **alınmadı**, çünkü kayıtta geçmiyorlar. Proposal v2'de yer alıyorlar; kaynakları hocanın feedback'i ve grup kararları ([kararlar.md](../kararlar.md)). Requirements dokümanına eklenmeden önce client'la teyit edilmeleri önerilir.

- AI ile okunan faturada belirsiz değerlerin işaretlenmesi ve kaydedilmeden önce kullanıcı onayı
- Rol bazlı yetkilendirme, kimlik doğrulama
- Değişiklik kaydı (audit log), günlük yedek
- "Real-time" yerine ölçülebilir veri gecikmesi
- Yeni POS'un KerzzPOS'un yerine geçmesi ve mali cihaz (ÖKC) arayüzü
