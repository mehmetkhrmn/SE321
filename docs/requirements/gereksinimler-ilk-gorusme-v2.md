# Gereksinimler v2: 15.10.2026 Client Görüşmesi (Genişletilmiş)

**Kaynak:** 15.10.2026 tarihli client görüşmesinin ses kaydı (~25:38). Görüşülen kişi: Mustafa Ulukaya, Financial Director, Rise Group.
**Önceki sürüm:** [gereksinimler-ilk-gorusme.md](gereksinimler-ilk-gorusme.md) (14 FR, 9 NFR). Bu sürüm onun yerine geçmez, onu genişletir. Eski ve yeni madde numaralarının eşleşmesi en altta.

**v1'den farkı**
- v1'de birleştirilmiş maddeler, ayrı ayrı test edilebilsin diye bölündü (ör. "raporlama" → gün sonu kasa, ciro, aylık kârlılık).
- Client'ın anlattığı **mevcut iş akışından** çıkan gereksinimler eklendi (talep-onay, mal kabul, iade, depo yeri, roller vb.).
- Kural aynı: kayıtta geçmeyen hiçbir özellik eklenmedi. Her maddenin altında alıntı ve zaman damgası var.

**Etiketler**
- **[Açık]**: Client ya da ekip açıkça istedi/sordu, client onayladı.
- **[Süreç]**: Client bugünkü işleyişi anlattı. Yeni sistemin bu işi desteklemesi gerekiyor, ama client "isterim" demedi. **Teyit edilmeli.**
- ⚠️: Kayıtta çelişkili ya da client'ın cevabı belirsiz.

**Kaynak notları:** Alıntılar ses kaydının otomatik transkriptinden birebir alındı. Kelime hataları olabilir; anlaşılmayan yerler `[…]` ile kısaltıldı, köşeli parantez içindeki notlar bize ait. Transkriptte konuşmacı ayrımı yok; "Client" ve "Ekip" etiketleri bağlamdan çıkarıldı. Zaman damgası biçimi `[dd:ss]`.

---

## Client'ın Öncelik Sırası

**(1) Cari ve kasa, (2) fatura/irsaliye, (3) stok.**

Kaynak/Zaman Damgası:
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..." `[24:42]`: "Çok doğru bir şekilde ilerlemesi gerekiyor."
- Client, `[24:56]`: "...fatura biriminde, faturalar da doğru düzgüne girilmesi için." `[24:59]`: "Onlar vazgeçilmez şeyler."
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..." `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."

---

## 1. Fonksiyonel Gereksinimler

### 1.1 Cari Hesap

**FR-01 [Açık]: Cari hareket kaydı**
- Sistem cari hesap hareketlerini kaydetmelidir.

Kaynak/Zaman Damgası:
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..."
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..."

**FR-02 [Süreç]: Cari dökümü**
- Sistem cari hesap dökümü (hareket listesi) verebilmelidir. Bugün bu döküm Netsis'te alınıyor.

Kaynak/Zaman Damgası:
- Client, `[03:45]`: "Netsis burada fatura, cari dökümü vesaire." `[03:49]`: "Burada takip ediliyor."

### 1.2 Kasa

**FR-03 [Açık]: Kasa kayıtları**
- Sistem kasa kayıtlarını tutmalıdır. Mevcut "kasa programı" işlevi korunmalıdır.

Kaynak/Zaman Damgası:
- Client, `[25:01]`: "Yani cari, hareket kayıtları, kasa kayıtları..."
- Ekip, `[09:20]`: "Korunması gereken bir özellik almak istiyorum." Client, `[09:38]`: "Tabi ki kasaprogramın özellikle."

**FR-04 [Açık]: Nakit ve kredi kartı ayrımı**
- Sistem kasa hareketlerini nakit ve kredi kartı olarak ayrı ayrı göstermelidir.

Kaynak/Zaman Damgası:
- Client, `[14:30]`: "Özellikle kasanın akit, kredi kartı, girişler çıkışlar."

**FR-05 [Açık]: Kasa giriş ve çıkışları**
- Sistem kasaya yapılan girişleri ve kasadan yapılan çıkışları kaydetmelidir.

Kaynak/Zaman Damgası:
- Client, `[14:30]`: "Özellikle kasanın akit, kredi kartı, girişler çıkışlar."

### 1.3 Raporlama

**FR-06 [Açık]: Gün sonu kasa raporu**
- Sistem her gün sonunda nakit, kredi kartı, giriş ve çıkışları gösteren bir kasa raporu üretmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[14:17]`: "Her gün sonu görmek istediğiniz bir rapor vesaire oluyor mu?" Client, `[14:27]`: "Var zaten." `[14:30]`: "Özellikle kasanın akit, kredi kartı, girişler çıkışlar." `[14:36]`: "Evet, seni görebiliyoruz zaten KerzzPOS sisteminde."

**FR-07 [Açık]: Ciro raporları**
- Sistem ciro raporları üretmelidir. Client bunu korunması gereken özellik olarak saydı.

Kaynak/Zaman Damgası:
- Ekip, `[09:20]`: "Korunması gereken bir özellik almak istiyorum." Client, `[09:36]`: "Cirolar, cirolar, cirolar."

**FR-08 [Açık]: Ayrıntılı raporlama**
- Sistemin raporlaması en az mevcut KerzzPOS kadar ayrıntılı olmalıdır.

Kaynak/Zaman Damgası:
- Client, `[07:36]`: "Ya da mesela Kerzz'de raporlama kısmında" `[07:39]`: "daha ayrıntılı bir ton istediğinin" `[07:41]`: "her raporu veriyor yani." `[07:43]`: "Çoğu rapor çıkıyor."
- Client, `[13:09]`: "Yani Kerzz kadar aktif değil, verimli değil dediği gibi raporlar vs. hiç yok gibi bir şey." [Bırakılan Mobrez için.]

**FR-09 [Açık]: Aylık finans ve kârlılık raporu**
- Sistem finans birimi için aylık rapor ve kârlılık raporu üretebilmelidir.

Kaynak/Zaman Damgası:
- Client, `[16:01]`: "Hem finansda raporlama, aylık raporlama dediğimiz var bizim karlılık vesaire de."

**FR-10 [Süreç]: Satın almadan finansa raporlama**
- Satın alma müdürünün girdiği veriler, finans/yönetim tarafından rapor olarak görülebilmelidir.

Kaynak/Zaman Damgası:
- Client, `[22:02]`: "Bu veriler satın alınacı tarafından gidiliyor." `[22:08]`: "Onun tarafından gidiliyor." `[22:10]`: "En son bizlere rapor ediliyor."

### 1.4 Fatura

**FR-11 [Açık]: PDF fatura yükleme**
- Kullanıcı gelen tedarikçi faturasını PDF olarak sisteme yükleyebilmelidir.

Kaynak/Zaman Damgası:
- Client, `[01:13]`: "Şimdi bizim en büyük problemimiz, fatura geldiğinde o faturayı isteme işlemek bizim için çok büyük bir problem."
- Client, `[01:29]`: "Fatura geldi, pdf şeklinde içine attık."

**FR-12 [Açık]: Faturanın otomatik işlenmesi**
- Sistem yüklenen PDF faturanın içeriğini otomatik olarak okuyup kaydetmelidir. Client "yapay zekâ tarzı" bir çözümden bahsetti.

Kaynak/Zaman Damgası:
- Client, `[01:25]`: "O süreçte böyle yapay zekalindeki hastanın tarzını da mesela atıyorum." `[01:32]`: "O direk Netsis'e ya da herhangi bir yere işleyebiliyorsa, mesela öyle bir sistem olur."

**FR-13 [Açık]: İşlenen faturanın Netsis'e aktarılması**
- İşlenen fatura verisi Netsis'e aktarılabilmelidir.

Kaynak/Zaman Damgası:
- Client, `[01:32]`: "O direk Netsis'e ya da herhangi bir yere işleyebiliyorsa, mesela öyle bir sistem olur."
- Client, `[02:25]`: "Ama tabii ki bu dediğim gibi tekrardan Netsis'e işlenmiyor."

**FR-14 [Açık]: Kalem bazında birim tutar**
- Fatura girişinde her kalem için birim tutar kaydedilmelidir.

Kaynak/Zaman Damgası:
- Client (bağlamdan), `[19:22]`: "Her zaman böyle birim tutarına giriyorsun."

**FR-15 [Açık]: Faturaya göre değişen iskonto**
- Fatura girişinde iskonto kaydedilebilmelidir. İskonto her faturada farklı olabilir; sistem sabit iskonto varsaymamalıdır.

Kaynak/Zaman Damgası:
- Client (bağlamdan), `[19:24]`: "Biraz daha mesela yanlar hatununda iskonto kısmı var." `[19:28]`: "İskonto kısmına giriyorsun." `[19:29]`: "Her zaman aynı iskonto öyle gelmedi." `[19:32]`: "Fatur'a direk entegre ettiğin zaman aslında onu da..."

**FR-16 [Süreç]: Alış faturasıyla stoğa giriş**
- Girilen alış faturasındaki ürünler stoğa eklenmelidir. Bugün KerzzPOS'ta alış faturası girilerek stok tutuluyor.

Kaynak/Zaman Damgası:
- Client, `[02:22]`: "Alınan alış faturaları giriliyor."
- Client, `[06:19]`: "Kerzz'e alış faturaları giriliyor." `[06:21]`: "Oradan da düşülüyor."
- Client, `[06:37]`: "O içine işlediği için tuşlama yaptıkça düşüyor."

**FR-17 [Süreç]: Tedarikçi kaydı**
- Faturalar ve teslimatlar ilgili tedarikçi firmayla ilişkilendirilmelidir.

Kaynak/Zaman Damgası:
- Client, `[04:40]`: "Tedarikçi firmadan hemen kapıda teslim alıyor."
- Client, `[18:38]`: "İşte 76'da ne var diyeceksin alkolü, soft içeceği, çerezi, işte gıda malzemeleri, tedarikçi firmalar gibi gibi."

### 1.5 İrsaliye ve Mal Kabul

**FR-18 [Açık]: İrsaliye kaydı**
- Sistem tedarikçiden gelen irsaliyeleri kaydetmelidir.

Kaynak/Zaman Damgası:
- Client, `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."

**FR-19 [Süreç]: Mal kabul kaydı**
- Depo sorumlusu tedarikçiden teslim aldığı malı sisteme işleyebilmelidir. Bugün malı kapıda teslim alıyor ve iki taraf da kaşe-imza atıyor.

Kaynak/Zaman Damgası:
- Client, `[04:11]`: "Malzeme geldiğinde satın almaya da depo sorumlusu karşılıyor malzemeye."
- Client, `[04:40]`: "Tedarikçi firmadan hemen kapıda teslim alıyor." `[04:43]`: "Hem Tedarikçi firma kaşeyimzağı yapıyor." `[04:47]`: "Hem bizler kaşeyimzağı yapıyoruz."
- ⚠️ Client, `[22:18]`: "Defolcuyla daha çok malları teslim alan kısımda." `[22:21]`: "O veri girmez." [Depo sorumlusu bugün veri girmiyor; kaydı kimin yapacağı teyit edilmeli.]

**FR-20 [Süreç]: İrsaliye fotoğrafı ile teyit**
- Mal geldiğinde irsaliyenin fotoğrafı sisteme yüklenebilmeli ve satın alma/finans tarafından görülüp teyit edilebilmelidir. Bugün bu iş WhatsApp üzerinden yapılıyor.

Kaynak/Zaman Damgası:
- Client, `[05:01]`: "Aynı şekilde mal geldiğine dair bir WhatsApp üzerinde bilgi veriyor." `[05:06]`: "Zaten fotoğra da gördüğümüz için," `[05:08]`: "İrsaliye ve fotoğra da gördüğümüz için o şekilde biz de teyit ediyoruz."

**FR-21 [Süreç]: Bozuk mal iadesi**
- Bozuk gelen mal için iade kaydı açılabilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[05:32]`: "Eksi gibi bozuk mal geldiği zaman ne yapıyorsunuz?"
- Client, `[05:35]`: "İyade." `[05:39]`: "Direkt geldiğimde bozuk." `[05:41]`: "Tabii ki iade süreci başlıyor."

**FR-22 [Süreç]: Depo yeri (bar / depo)**
- Teslim alınan malın nereye konduğu kaydedilebilmelidir: bar ya da -2. kattaki depo.

Kaynak/Zaman Damgası:
- Ekip, `[04:51]`: "Depo sorumlusu onu nereye alıyor?"
- Client, `[04:54]`: "Ya barın içine alıyor ya da depo var aşağıda." `[04:57]`: "Eksi iki de." `[04:59]`: "Depo da muhafaza ediyor."

### 1.6 Talep ve Sipariş

**FR-23 [Süreç]: Malzeme talebi oluşturma**
- Barmen ve mutfak şefi ihtiyaç duydukları malzemeyi (ör. alkol, soft içecek) sistem üzerinden talep edebilmelidir. Bugün bu iş WhatsApp grubundan yapılıyor.

Kaynak/Zaman Damgası:
- Client, `[02:50]`: "Bir WhatsApp grubumuz var." `[02:52]`: "O WhatsApp grubu üzerinden ilerleniyor zaten."
- Client, `[02:56]`: "Barmen ya da mutfak şefe taleplerini." `[02:59]`: "Barmen mesela alkol, soft içecekleri bildiriyor."

**FR-24 [Süreç]: Satın alma onayı**
- Satın alma birimi gelen talepleri onaylayabilmelidir.

Kaynak/Zaman Damgası:
- Client, `[03:04]`: "Satın alma birimi de bunu onaylıyor."

**FR-25 [Süreç]: Haftalık sipariş planlama**
- Sistem siparişlerin haftalık olarak planlanmasını desteklemelidir.

Kaynak/Zaman Damgası:
- Ekip, `[02:43]`: "Şuradan şu kadar satış ederiz." Client, `[02:46]`: "Haftalık planlama şeklinde gidiyor."
- Client, `[03:07]`: "O şekilde haftalık bir isim var."

**FR-26 [Açık]: Stok azalınca tedarikçiye otomatik mesaj**
- Stok azaldığında sistem tedarikçiye elektronik ortamda otomatik bir sipariş/bildirim mesajı gönderebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[12:09]`: "Diyelim ki stoğumuz azalmaya başladı." `[12:13]`: "Siz tedarikçinize otomatik olarak bildirmesini ister misiniz?"
- Client, `[12:23]`: "Üstelik ortamda isterim." `[12:26]`: "Çünkü elektronik düştüğümde direk bir mesaj olacak." ["Elektronik ortamda isterim" olarak anlaşılıyor.]

### 1.7 Stok

**FR-27 [Açık]: Stok takibi**
- Sistem stok takibi yapmalıdır.

Kaynak/Zaman Damgası:
- Client, `[25:06]`: "Fatura, irsaliye, fatura, stok bölümü..."
- Client, `[07:33]`: "Mesela stok takip vesaire yapmıyor onların çoğu." [Alternatif sistemlerin eksikliği olarak.]

**FR-28 [Açık]: Satışta otomatik stok düşümü**
- Her ödeme yapıldığında satılan ürünler stoktan otomatik düşülmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[14:39]`: "Peki yeni oluşturulacak sistemin POS yazılımınıza yani daha doğrusu adisyon sisteminizi entegri olmasını ister misiniz?"
- Client, `[14:55]`: "Her ödeme yapıldığında POS yazılımının adisyonu entegre çalışması ve arkada stock systemleri rejimli olup, stock'tan düşürülmesi."

**FR-29 [Açık]: Masa bazlı adisyon**
- Her masanın bir adisyon fişi olmalı; adisyonda istenen ürünler görünmelidir. Stok düşümü bu adisyondan yapılmalıdır.

Kaynak/Zaman Damgası:
- Client, `[14:48]`: "Neticede bir adisyon fişi belledir her masanın." `[14:52]`: "Ürün, istenen ürün belledir."

**FR-30 [Süreç]: Koli → adet/şişe dönüşümü**
- Sistem koli olarak gelen ürünü stokta adet/şişe olarak tutabilmelidir. Bugün koli içindeki adetle elle çarpılıyor.

Kaynak/Zaman Damgası:
- Ekip, `[07:44]`: "Siz bir de hani içecekleri stokta tutarken" `[07:48]`: "şey kolyo kolyo olarak mı tutuyorsunuz?" `[07:51]`: "Yoksa şişe o sayısını mı biliyorsunuz direkt?"
- Client, `[07:58]`: "Yani bir kolyo geliyor çarpıyoruz."
- Client, `[04:23]`: "İki koli, Chivas 18 geldi."

**FR-31 [Süreç]: Ürün grupları**
- Ürünler türüne göre gruplanabilmelidir: alkol, soft içecek, çerez, gıda malzemesi.

Kaynak/Zaman Damgası:
- Client, `[18:38]`: "İşte 76'da ne var diyeceksin alkolü, soft içeceği, çerezi, işte gıda malzemeleri, tedarikçi firmalar gibi gibi."

**FR-32 [Açık]: Kritik stok eşiği**
- Her ürün için bir kritik stok seviyesi tanımlanabilmelidir (ör. soft içecek için 50).

Kaynak/Zaman Damgası:
- Client, `[03:12]`: "Atıyorum mesela soft içecekler de." `[03:14]`: "50'nin altına düştü mesela."

**FR-33 [Açık]: Kritik stok uyarısı**
- Bir ürün kritik seviyenin altına düştüğünde sistem kullanıcıya uyarı vermelidir.

Kaynak/Zaman Damgası:
- Client, `[03:09]`: "Mesela Kerzz'de atıyorum." `[03:10]`: "Ürün bittiğinde bize bildirim tarzına bir şey gelmiyor." `[03:16]`: "Bize böyle bir uyarı şeklinde," `[03:18]`: "gelebilirsiniz diye bir şey olursa mesela."

**FR-34 [Açık]: Stok sayımı**
- Sistem şube bazında stok sayımı yapılmasını ve sayım sonuçlarının sistemde tutulmasını desteklemelidir. Bugün sayımlar Excel'e dökülüyor.
- Sayım haftalık yapılabilecek kadar kolay olmalıdır (süre: NFR-08).

Kaynak/Zaman Damgası:
- Client, `[08:51]`: "Excel'e dökülüyor sayınlar vesaire."
- Client, `[17:31]`: "Aylık oluyor." `[17:36]`: "Mesela bu sistemle haftalık olsa süper olur." `[17:39]`: "Evet, haftalık sayıda."

**FR-35 [Açık] ⚠️: Şubeler arası malzeme transferi**
- Sistem bir şubeden diğerine yapılan malzeme transferini kaydedip takip edebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[24:12]`: "Bunların arasında malzemelaş verişi yapıyorsunuz galiba." `[24:17]`: "Yapıyor musunuz?" Client, `[24:18]`: "Evet."
- Ekip, `[24:23]`: "Başka bir restoranları istenebilir." `[24:25]`: "Diğerine götürülebilir." `[24:27]`: "O sistem üzerinden takip ederiz." Client, `[24:29]`: "Evet."
- **Çelişki:** Ekip, `[11:05]`: "Sizin farklı şubeler arasında malzeme transferi vesaire oluyor mu?" Client, `[11:14]`: "Yok şey malzeme içi normal."

**FR-36 [Açık]: Maliyet verisi entegrasyonu** *(client: "olursa iyi olur")*
- Sistem maliyet verilerini doğrudan alabilecek şekilde entegre çalışmalıdır.

Kaynak/Zaman Damgası:
- Client, `[15:06]`: "Aynı zamanda maliyet için de bir entegrasyon şartı lazım." `[15:09]`: "Direkt maliyetin verileri alabildiği bir entegrasyon sistemi yaptılar." `[15:14]`: "Yani o da oluşta iyi olur." [= olursa iyi olur]

### 1.8 Sistemler Arası Veri Akışı

**FR-37 [Açık]: Satış verisinin elle aktarılmaması**
- POS'taki satış verileri Excel üzerinden elle aktarılmadan diğer modüllere (stok, raporlama) ve muhasebeye ulaşmalıdır.

Kaynak/Zaman Damgası:
- Client, `[02:15]`: "Elektronik ortama Excel yönünden aktarıyor." `[02:18]`: "KerzzPOS sisteminden satışlar çekiliyor."
- Client, `[02:28]`: "Sadece KerzzPOS üzerinden ve Excel, manuel olarak ilerliyor."

**FR-38 [Açık]: POS ve muhasebe verisinin tutarlı olması**
- Satış ve muhasebe tarafındaki veriler birbiriyle uyumlu olmalı; bir tarafı sistemin, diğer tarafı insanın yönettiği ayrı takip ortadan kalkmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[05:48]`: "İkisi senin birbiriyle entegrasyonu var mı?" Client, `[05:53]`: "Bağımsı kullanıyoruz."
- Client, `[08:19]`: "Ya zaten veriler birbirlerine uyumuyor."
- Client, `[08:39]`: "Dediğim gibi tek sıkıntımız konuşmaması." `[08:42]`: "İntegrasyonu asla yok."
- Ekip, `[08:59]`: "İkisayrı yerde takip edelim." `[09:01]`: "Birini sistem yönetirken diğerini insan yönettiği için." `[09:04]`: "Çalışmaları yaşanıyor." Client, `[09:06]`: "Doğru."

**FR-39 [Açık]: Tek sistemde birleşik kullanım** *(client'ın "hayal" olarak anlattığı)*
- Satış (POS) ve muhasebe tarafı personel için tek bir sistemden kullanılabilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[15:31]`: "Hayal ettiğiniz ama çok zor olur diye söylemekten çekiniz bir şey var mı?"
- Client, `[15:54]`: "Hem Netsis ya da Kerzz ile Netsis." `[15:57]`: "Tek sistemde olsa hem arkadaşlarımız için çok rahat olur." `[16:07]`: "Çok rahat ve çok muhteşem, vav bir şey olur bizim için."

### 1.9 Kullanıcılar ve Roller

**FR-40 [Süreç]: Kullanıcı rolleri**
- Sistem bugünkü rolleri karşılayacak kullanıcı tiplerini desteklemelidir:
  - finans (raporları görür)
  - satın alma müdürü (veri girer, sipariş verir, onaylar)
  - depo sorumlusu (malı teslim alır)
  - barmen ve mutfak şefi (talep eder)

Kaynak/Zaman Damgası:
- Client, `[00:12]`: "Ağırlıklı muhasebe, finans birimi de aynı şekilde sorumlusuz."
- Client, `[00:47]`: "Mutfak şefi gibi, onun üstünde satın alma müdürümüz var." `[00:52]`: "Depo sorumlumuz var, o şekilde tarihları ilerliyor." `[00:57]`: "Komi, garson, barboy var onun altında, o şekilde ilerliyor."
- Client, `[22:02]`: "Bu veriler satın alınacı tarafından gidiliyor." `[22:05]`: "Zaten siparişleri veren doğudur olmayı ile en son."
- Client, `[22:18]`: "Defolcuyla daha çok malları teslim alan kısımda." `[22:21]`: "O veri girmez."

---

## 2. Non-Fonksiyonel Gereksinimler

### 2.1 Güvenlik

**NFR-01 [Açık]: Mevcut sistemden güçlü güvenlik altyapısı**
- Client mevcut KerzzPOS'un güvenlik duvarını yetersiz buluyor. Yeni sistemin güvenlik altyapısı daha güçlü olmalı ve dış saldırılara karşı korumalı olmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[09:42]`: "Peki en major probleminiz nedir bu sistemdeki, eski sistemdeki ve en büyük probleminiz nedir?"
- Client, `[10:10]`: "[…] Bir güvenlik duvarı oluşmunda mesela en büyük problemleri o. Bence güvenlik" `[10:15]`: "duvara hala söylüyorum. Yıllı 2026'i KerzzPOS'un güvenlik duvarı iyi bir donanın değil." `[10:20]`: "Değil. Net olarak söyleyebiliyorum."
- *Not: Client bu bölümde geçmişte yaşanan bir güvenlik olayından da bahsediyor (`[10:02]`). Repo public olduğu için ayrıntısı buraya alınmadı.*

**NFR-02 [Açık] ⚠️: Hassas verilerin korunması**
- Alış fiyatları, tedarikçi anlaşmaları, kâr marjları ve satış fiyatları hassas veri olarak korunmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[19:01]`: "Tutmandığınız sistemdeki biraz da hassas olan bilgiler." `[19:10]`: "Alışfiyatlarınız olabilir çünkü tedarikçi ile anlaşıyorsunuz." `[19:13]`: "Tedarikçi ile anlaşmaları yine dediğim gibi veya kar marjları satılıyorum da." `[19:17]`: "Soft içeceğin size gelişi farklıdır." `[19:19]`: "Satış fiyatı farklıdır."
- *Ekip sordu; client'ın cevabı (`[19:22]`–`[19:32]`) iskontoya geçiyor, erişim kısıtlaması açıkça istenmedi.*

### 2.2 Doğruluk

**NFR-03 [Açık]: Cari ve kasa doğruluğu**
- Cari ve kasa kayıtları hatasız tutulmalıdır.

Kaynak/Zaman Damgası:
- Client, `[24:39]`: "İlk isteyeceğin kesinlikle cari ve kasa programı..." `[24:42]`: "Çok doğru bir şekilde ilerlemesi gerekiyor."

**NFR-04 [Açık]: Fatura doğruluğu**
- Faturalar sisteme doğru girilmelidir.

Kaynak/Zaman Damgası:
- Client, `[24:56]`: "...fatura biriminde, faturalar da doğru düzgüne girilmesi için." `[24:59]`: "Onlar vazgeçilmez şeyler."

**NFR-05 [Açık]: Stok doğruluğu**
- Stok kayıtları gerçek stokla uyumlu olmalıdır. Mevcut KerzzPOS'taki "%100 doğru olmayan" stok sorunu yeni sistemde olmamalıdır.

Kaynak/Zaman Damgası:
- Client, `[03:35]`: "Tabii ki, KerzzPOS dediğim gibi." `[03:37]`: "Orada stok ve yüzde yüz verilerle ilerlemiyor."
- Client, `[06:15]`: "Orada yani yüzde yüz verilerle takip edilmiyor tabii ki."

### 2.3 Kapasite ve Performans

**NFR-06 [Açık]: Haftalık fatura hacmi**
- Sistem yoğun sezonda haftada 70-80 tedarikçi faturasını işleyebilmelidir.

Kaynak/Zaman Damgası:
- Client, `[18:33]`: "Bu hafta gelen faturası ise 76 […]" `[18:46]`: "Yani 70'de 80'in fotoğruğu geliyor." `[18:56]`: "Bu haftalık."

**NFR-07 [Süreç]: Sezonluk ve hafta sonu yoğunluğu**
- Sistem yazın şubeler açıldığında artan fatura sayısını ve hafta sonu yoğunluğunu karşılayabilmelidir. Mal girişi haftada iki gün oluyor.

Kaynak/Zaman Damgası:
- Client, `[01:19]`: "Çünkü yazın, dükkanı açılıyor, birden bir fatura yılın oluyor mesela."
- Client, `[18:21]`: "Genelde haftalık iki gün, bizim özellikle hafta sonu çok iş oluyor."

**NFR-08 [Açık]: Sayım süresi**
- Stok sayımı bugünkü 4-5 saatten (aylık, 1-2 kişi) kısa sürmeli ve haftalık yapılabilir olmalıdır.

Kaynak/Zaman Damgası:
- Ekip, `[17:09]`: "Bir stock girişi ya da sayımı en fazla ne kadar sürmeli ki personel kullanabilirsin?"
- Client, `[17:20]`: "Ortalama bir iki kişi oluyor." `[17:25]`: "Yaklaşık 4-5 saat sürüyor."
- Ekip, `[17:40]`: "Yani ne hızlı olabilirse bu sistem bir haftaya kadar indirebilir o zaman." Client, `[17:44]`: "Kesinlikle."

### 2.4 Ölçek

**NFR-09 [Açık]: Çok şubeli kullanım**
- Sistem birden fazla işletmeyi aynı anda desteklemelidir: yazın 4-5, kışın 3.

Kaynak/Zaman Damgası:
- Ekip, `[00:24]`: "Toplamda kaç şube, kaç personel?" Client, `[00:26]`: "Yaklaşık, yazın aktif olarak 4-5, kışında 3 işletme var."

**NFR-10 [Süreç]: Sezona göre şube açma/kapama**
- Yazın açılıp kışın kapanan şubeler sisteme kolayca eklenip devre dışı bırakılabilmelidir.

Kaynak/Zaman Damgası:
- Client, `[00:26]`: "Yaklaşık, yazın aktif olarak 4-5, kışında 3 işletme var."
- Client, `[01:19]`: "Çünkü yazın, dükkanı açılıyor, birden bir fatura yılın oluyor mesela."

**NFR-11 [Süreç]: Personel ölçeği**
- Sistem yılda yaklaşık 250 personelin çalıştığı bir yapıya uygun olmalıdır.

Kaynak/Zaman Damgası:
- Client, `[00:36]`: "Toplam yıl içerisinde yaklaşık 250 personeli buluyor."

### 2.5 Erişim

**NFR-12 [Açık]: Cihazlar**
- Sisteme mutfaktan, telefondan ve ofisten erişilebilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[16:59]`: "Sistemenlerden ve hangi cihazdan girecek?" Client, `[17:04]`: "Mutfakta vereceğimize." `[17:05]`: "Telefon, ofis..."

### 2.6 Geçiş ve Kullanılabilirlik

**NFR-13 [Açık]: Eğitimle öğrenilebilirlik**
- Eski sisteme alışkın personel, eğitim verildiğinde yeni sistemi kullanabilmelidir.

Kaynak/Zaman Damgası:
- Ekip, `[11:34]`: "Yeni bir sisteme geçiş var olan eski çalışanlarınızı zorlar mı?"
- Client, `[11:38]`: "Zorlayabilirim ketapta ama alışma süreçleri var." `[11:43]`: "Doğru eğitimini verildiği senaryoda süreç uzaması."

**NFR-14 [Açık]: Alışma süresi**
- Personelin yeni sisteme alışması en fazla 15 gün - 1 ay sürmelidir.

Kaynak/Zaman Damgası:
- Client, `[23:03]`: "Aslında risk tabi de bununla alışma süreci var." `[23:07]`: "Yani bu alışma süreci de biraz zaman alabilir." `[23:10]`: "On beş gün bir ay kadar."
- Client, `[23:18]`: "Çünkü bağır olan bir düzen var." `[23:22]`: "Bunu atlatabilmek kolay değil tabii ki."

**NFR-15 [Süreç]: İşlevsel yeterlilik**
- Sistem "Excel'in bir tık gelişmişi" kadar basit olmamalıdır. Daha önce bu yüzden bırakılan Mobrez'den farklı olarak stok takibi ve raporlama içermelidir.

Kaynak/Zaman Damgası:
- Client, `[13:05]`: "Orada bir Mobrez kullandık ama çok kısa süreli." `[13:09]`: "Yani Kerzz kadar aktif değil, verimli değil dediği gibi raporlar vs. hiç yok gibi bir şey." `[13:17]`: "Manuel gibi, çok basitleştirilmiş bir sistem yapmış." `[13:21]`: "Excel'in bir tık daha hali gibi."
- Client, `[07:28]`: "Alternatifler var ama diğer mesela yazar kasapol şeyleri" `[07:31]`: "bu kadar yani Kerzz kadar donanımlı değil." `[07:33]`: "Mesela stok takip vesaire yapmıyor onların çoğu."

### 2.7 Destek, Süreklilik ve Ticari Kısıtlar

**NFR-16 [Süreç]: 7/24 uzaktan destek**
- Sorunlara günün her saatinde uzaktan bağlantıyla müdahale edilebilmelidir. Client bunu mevcut sistemin işe yarayan bir yanı olarak anlattı.

Kaynak/Zaman Damgası:
- Client, `[13:56]`: "Şimdi şöyle 7-20'lü uzaktan bağlantıyla hizmet veriyorlar." `[14:00]`: "Yani bu hafta sonunda olsa, gece 5'de olsa, 3'de olsa bir hizmet olduğu için uzaktan hemen […]" `[14:10]`: "Genelde çoğu zaman hallediyor yani problem."

**NFR-17 [Süreç]: Ödeme gecikmesinde sistemin kapatılmaması**
- Ödeme gecikmesi gibi ticari bir sebeple sistem hemen kapatılmamalıdır. Client mevcut sağlayıcının bu uygulamasından şikâyetçi.

Kaynak/Zaman Damgası:
- Client, `[21:36]`: "İkince vesaire direkt mesel sistem kapanıyor." `[21:41]`: "Ücreti alamadınız ama mesela direkt hemen sistemi kapatıyor." `[21:51]`: "Memleketimin insanı yapsaydı böyle olmuyor." `[21:53]`: "Parayı faizle düşürürdü ama yine sistem çalışır oluyor."

**NFR-18 [Süreç] ⚠️: Ana sunucuya bağımlılık**
- Mevcut sistemde ana sunucu olmadığında terminaller çalışmıyor. Yeni sistemde tek bir sunucunun durması şubelerdeki çalışmayı durdurmamalıdır.
- *Client bunu doğrudan şikâyet olarak söylemedi; mevcut yapıyı anlatırken geçti.*

Kaynak/Zaman Damgası:
- Ekip, `[10:27]`: "Peki, sistem lokal mi çalışıyor? Yani burada restoranla mı çalışıyor, yoksa siz mi bağlanıyorsunuz uzaktan?"
- Client, `[10:42]`: "Şimdi bir tane ana sunucu var." `[10:45]`: "Aşağıdakiler de terminer gibi." `[10:48]`: "O zaman lokal işleniyor, günün sonunda ana sunucuya gidiyor gibi." `[10:53]`: "Yani hepsi birbirleri integre yani ama ana sunucu olmadığı zaman diğerleri çalışmıyor mesela."

**NFR-19 [Açık]: Kurulum + aylık bakım modeli**
- Client ilk kurulum ücreti ve ardından aylık bakım ücreti modelini kabul edilebilir buluyor.
- *Tutarlar kayıtta geçiyor (`[13:47]`, `[21:10]`–`[21:16]`); repo public olduğu için buraya alınmadı.*

Kaynak/Zaman Damgası:
- Client, `[13:36]`: "İlk başta kurulumun için vs. para alıyorlar." `[13:39]`: "Aylık sonrasında." `[13:41]`: "Bunu bakımla alıyorlar."
- Client, `[21:21]`: "Aylık bakım ücreti tabi bu."

---

## 3. Tartışılan Ama Gereksinim Olarak Alınmayanlar

| Konu | Neden alınmadı | Kaynak/Zaman Damgası |
|---|---|---|
| Fire, bozulma ve SKT'nin elektronik takibi | Bugün manuel; client istemedi. Ürünler "bozulacak kadar durmuyor". | Client, `[03:26]`: "Yok, manuel."; `[20:23]`: "Bozulacak kadar durmuyor zaten." |
| Gıda denetimi kayıtları (SKT, soğuk zincir, alkol ruhsatı) | Client "muhtemelen vardır" dedi; ne tutulacağı belirsiz. **Açık soru.** | Client, `[19:48]`: "Muhtemelen vardır."; `[20:15]`: "Zaten ürünleri alırken seykatelerine bakıyorlar." [= sertifikalarına] |
| Yapay zekâ ajanları (stok, sipariş, depo) | Ekibin fikri; client istemedi. | Ekip, `[16:36]`–`[16:45]` |
| Kamera ile stok takibi | Ekip önerdi; client sadece "Olabilir" dedi. | Ekip, `[17:45]`–`[18:09]`; Client, `[18:10]`: "Olabilir." |
| Yedekleme | Ekip örnek olarak saydı; client açık bir talepte bulunmadı. | Ekip/Client, `[09:48]`–`[09:57]` |

## 4. Kayıtta Olmayan, Proposal'dan / Hoca Feedback'inden Gelen Maddeler

Bu maddeler kayıtta geçmiyor, bu listeye **alınmadı**. Kaynakları hocanın feedback'i ve grup kararları ([kararlar.md](../kararlar.md)); client'la teyit edilmeleri önerilir.

- AI ile okunan faturada belirsiz değerlerin işaretlenmesi ve kaydedilmeden önce kullanıcı onayı
- Rol bazlı yetkilendirme, kimlik doğrulama
- Değişiklik kaydı (audit log), günlük yedek
- "Real-time" yerine ölçülebilir veri gecikmesi
- Yeni POS'un KerzzPOS'un yerine geçmesi ve mali cihaz (ÖKC) arayüzü

## 5. v1 → v2 Eşleşmesi

| v1 | v2 |
|---|---|
| FR-01 Cari hareketleri | FR-01, FR-02 |
| FR-02 Kasa kayıtları | FR-03, FR-04, FR-05 |
| FR-03 Raporlama | FR-06, FR-07, FR-08, FR-09 (+ yeni FR-10) |
| FR-04 PDF fatura | FR-11, FR-12 |
| FR-05 Birim tutar / iskonto | FR-14, FR-15 |
| FR-06 İrsaliye | FR-18 (+ yeni FR-19, FR-20, FR-21, FR-22) |
| FR-07 Satışta stok düşümü | FR-27, FR-28, FR-29 |
| FR-08 Birim dönüşümü | FR-30 |
| FR-09 Kritik stok uyarısı | FR-32, FR-33 |
| FR-10 Tedarikçiye otomatik mesaj | FR-26 |
| FR-11 Stok sayımı | FR-34 |
| FR-12 Şubeler arası transfer | FR-35 |
| FR-13 Maliyet entegrasyonu | FR-36 |
| FR-14 Çift girişin kalkması | FR-13, FR-37, FR-38, FR-39 |
| - | Yeni: FR-16, FR-17, FR-23, FR-24, FR-25, FR-31, FR-40 |
| NFR-01 Güvenlik | NFR-01 |
| NFR-02 Hassas veri | NFR-02 |
| NFR-03 Doğruluk | NFR-03, NFR-04, NFR-05 |
| NFR-04 Kapasite | NFR-06, NFR-07 |
| NFR-05 Sayım süresi | NFR-08 |
| NFR-06 Çok şube | NFR-09, NFR-10, NFR-11 |
| NFR-07 Cihazlar | NFR-12 |
| NFR-08 Geçiş | NFR-13, NFR-14 |
| NFR-09 Destek | NFR-16, NFR-17 |
| - | Yeni: NFR-15, NFR-18, NFR-19 |
