# Proje Kararları

Grubun aldığı kapsam ve tasarım kararları. Requirements ve tasarım aşamalarında buna göre ilerlenecek.

| # | Tarih | Karar | Gerekçe | Nereye yansıyacak |
|---|---|---|---|---|
| K1 | 25.10.2026 | Yeni sistem **KerzzPOS'un yerine geçecek**; **Netsis** resmi muhasebe olarak kalacak, onaylı kayıtlar import dosyasıyla Netsis'e aktarılacak. | Üçüncü bir sistem eklenmeden veri tek yerde doğsun (sistem bütünlüğü). Hoca ikisini birden değiştirmememizi istedi; client Netsis'ten memnun. | Proposal v2 ✅ |
| K2 | 25.10.2026 | Yeni POS, KerzzPOS'un client'ın beğendiği yanlarını koruyacak (ayrıntılı günlük ciro ve kasa raporları) ve client'ın olmazsa olmazlarını ekleyecek. | Client Kerzz'in raporlamasını övdü; "ciro raporları, kasa programı korunmalı" dedi. | Proposal v2 ✅; requirements: korunacak rapor/ekran listesi (Kerzz ekran fotoğraflarından) |
| K3 | 25.10.2026 | Yazarkasa (Yeni Nesil ÖKC) bağlantısı **simüle edilecek**: tasarımda ayrı bir "mali cihaz arayüzü" bileşeni olacak; prototipte arkasında sahte (mock) bir modül fişi ekranda gösterecek / kaydedecek. | Gerçek cihaz bağlantısı (üretici SDK'sı, sertifika) bir dönemlik projede gerçekçi değil; "kapsam dışı" demek çift veri girişini geri getirirdi. | Requirements (kısıt + varsayım), tasarım (arayüz + mock) |

## Requirements aşamasında kontrol edilecekler

- ÖKC ve e-Adisyon mevzuatının restoranlar için güncel durumu.
- Client'a: şu an hangi yazarkasa cihazı kullanılıyor, Kerzz'le nasıl bağlı?
