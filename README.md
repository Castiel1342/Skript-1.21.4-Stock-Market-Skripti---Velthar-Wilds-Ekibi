================================================================================
                    STOCK SİSTEMİ - KULLANIM KILAVUZU
                      Geliştirici: Velthar Wilds
================================================================================

İÇİNDEKİLER:
1. Sistem Hakkında
2. Özellikler
3. Kurulum
4. Oyuncu Komutları
5. Admin Komutları
6. Sistem Ayarları
7. Ürün Ekleme Rehberi
8. Nadirlik Sistemi
9. Stok Yenileme Mekanizması
10. Sorun Giderme

================================================================================
1. SİSTEM HAKKINDA
================================================================================

Bu skript, Minecraft sunucunuz için gelişmiş bir market/mağaza sistemidir.
Otomatik stok yenileme, nadirlik sistemi, hediye gönderme ve sayfalama
özellikleri içerir. Ekonomi sistemi olarak VEC (Gem/Mücevher) kullanır.

Gereksinimler:
- Skript eklentisi
- LuckPerms (rütbe gösterimi için)
- VEC ekonomi sistemi (veya uyumlu ekonomi eklentisi)

================================================================================
2. ÖZELLİKLER
================================================================================

✓ Otomatik Stok Yenileme (Varsayılan: 2 saatte bir)
✓ 10 Sayfa Destek (Her sayfada 8 ürün slotu)
✓ Nadirlik Sistemi (Sıradan, Efsanevi, Tanrısal)
✓ Hediye Gönderme Özelliği
✓ Gerçek Zamanlı Saat Göstergesi
✓ Profil ve Cüzdan Bilgisi
✓ Stok Tükenme Sistemi
✓ Onay Menüsü (Yanlış alım önleme)
✓ Özelleştirilebilir Ses Efektleri

================================================================================
3. KURULUM
================================================================================

1. Skripti sunucunuzun /plugins/Skript/scripts/ klasörüne koyun
2. Skripti yüklemek için /sk reload <dosya_adi> komutunu kullanın
3. İlk stok yenileme otomatik olarak başlayacaktır
4. Ürün eklemek için admin komutlarını kullanın

================================================================================
4. OYUNCU KOMUTLARI
================================================================================

/stock [sayfa_numarası]
├─ Açıklama: Market menüsünü açar
├─ Örnek: /stock 1
├─ Sayfa belirtilmezse 1. sayfa açılır
└─ Toplam 10 sayfa mevcut (1-10)

Market Menüsü Özellikleri:
├─ Yeşil Panel: Satın Al
├─ Sarı Panel: Hediye Et
├─ Profil Butonu: Oyuncu bilgileri
├─ Cüzdan Butonu: Bakiye gösterimi
├─ Bilgi Rehberi: Sistem açıklamaları
├─ Ok Butonları: Sayfa gezinme
└─ Saat: Kalan yenileme süresi

Satın Alma:
1. İstediğiniz ürünün yanındaki yeşil panele tıklayın
2. Onay menüsünde "ONAYLA" butonuna basın
3. Ürün envanterinize eklenecektir

Hediye Gönderme:
1. Ürünün yanındaki sarı panele tıklayın
2. Açılan sohbete hedef oyuncunun ismini yazın
3. Onay menüsünde "ONAYLA" butonuna basın
4. Ürün hedef oyuncuya gönderilir

================================================================================
5. ADMİN KOMUTLARI
================================================================================

/stockadmin
├─ İzin: op
└─ Açıklama: Admin panelini gösterir

/stockadmin yenile
├─ İzin: op
└─ Açıklama: Stokları manuel olarak yeniler

/stockadmin sil <sayfa> <sıra>
├─ İzin: op
├─ Örnek: /stockadmin sil 1 3
└─ Açıklama: Belirtilen sayfadaki ürünü siler

/itemekle <sıra> <sayfa> <fiyat> <minStok> <maxStok> <nadirlik>
├─ İzin: op
├─ Örnek: /itemekle 1 1 500 5 20 15
├─ Kullanım: Elinizde tuttuğunuz eşyayı markete ekler
└─ Parametreler:
    ├─ sıra: 1-8 arası slot numarası
    ├─ sayfa: 1-10 arası sayfa numarası
    ├─ fiyat: GEM cinsinden fiyat
    ├─ minStok: Minimum stok miktarı
    ├─ maxStok: Maximum stok miktarı
    └─ nadirlik: 1-20 arası nadirlik değeri

================================================================================
6. SİSTEM AYARLARI
================================================================================

Skript dosyasının başındaki "options:" bölümünden ayarlanabilir:

p: &8[&aStock&8] &f
├─ Sistem mesaj öneki
└─ Değiştirilebilir

refresh: 7200
├─ Stok yenileme süresi (saniye)
├─ Varsayılan: 7200 (2 saat)
└─ Örnek: 3600 = 1 saat, 14400 = 4 saat

bos_slot_adi: &c&lBOŞ SLOT
└─ Boş slot gösterge yazısı

gift_sound: entity.experience_orb.pickup
├─ Hediye alındığında çalan ses
└─ Minecraft ses ID'si kullanılır

================================================================================
7. ÜRÜN EKLEME REHBERİ
================================================================================

ADIM ADIM ÜRÜN EKLEME:

1. İstediğiniz eşyayı elinize alın
2. Aşağıdaki komutu kullanın:
   /itemekle <sıra> <sayfa> <fiyat> <minStok> <maxStok> <nadirlik>

ÖRNEK SENARYOLAR:

Örnek 1: Sıradan Bir Eşya
/itemekle 1 1 100 10 50 5
├─ Slot: 1, Sayfa: 1
├─ Fiyat: 100 GEM
├─ Stok: 10-50 arası
└─ Nadirlik: 5 (Sıradan)

Örnek 2: Efsanevi Eşya
/itemekle 3 2 1000 5 15 15
├─ Slot: 3, Sayfa: 2
├─ Fiyat: 1000 GEM
├─ Stok: 5-15 arası
└─ Nadirlik: 15 (Efsanevi)

Örnek 3: Tanrısal Eşya
/itemekle 5 1 5000 1 5 20
├─ Slot: 5, Sayfa: 1
├─ Fiyat: 5000 GEM
├─ Stok: 1-5 arası
└─ Nadirlik: 20 (Tanrısal)

================================================================================
8. NADİRLİK SİSTEMİ
================================================================================

Nadirlik Değerleri (1-20):

┌────────────┬─────────┬──────────────┬─────────────────────┐
│  Nadirlik  │  Değer  │ Stok Şansı   │     Görünüm         │
├────────────┼─────────┼──────────────┼─────────────────────┤
│  Sıradan   │  1-12   │    %100      │  &bNadir             │
│  Efsanevi  │  13-19  │    %60       │  &4Efsanevi          │
│  Tanrısal  │   20    │    %10       │  &4&l&ka TANRISAL   │
└────────────┴─────────┴──────────────┴─────────────────────┘

Stok Gelme Mantığı:

• Sıradan (1-12): Her yenilemede %100 stok gelir
• Efsanevi (13-19): %60 ihtimalle stok gelir, %40 tükenir
• Tanrısal (20): %10 ihtimalle stok gelir, %90 tükenir

Stok Miktarı:
• Sıradan: minStok ile maxStok arası tam rastgele
• Efsanevi: minStok ile %70 civarı
• Tanrısal: minStok ile %20 civarı

================================================================================
9. STOK YENİLEME MEKANİZMASI
================================================================================

Otomatik Yenileme:
├─ Her 2 saatte bir (7200 saniye)
├─ Sunucu genelinde duyuru yapılır
├─ Tüm stoklar sıfırlanır ve yeniden hesaplanır
└─ Nadirlik sistemine göre stok belirlenir

Manuel Yenileme:
└─ /stockadmin yenile komutu ile anında yenileme

Yenileme Sırasında:
├─ Açık menüler otomatik güncellenir
├─ Saat sayacı sıfırlanır
└─ Oyuncular bilgilendirilir

================================================================================
10. SORUN GİDERME
================================================================================

PROBLEM: Cüzdan bakiyesi gösterilmiyor
ÇÖZÜM: VEC eklentisinin doğru kurulduğundan emin olun
       PlaceholderAPI yüklü olmalıdır

PROBLEM: Rütbe "Oyuncu" olarak gözüküyor
ÇÖZÜM: LuckPerms doğru kurulu olmalı ve PlaceholderAPI expansion'ı indirilmeli
       /papi ecloud download LuckPerms

PROBLEM: Stoklar yenilenmiyor
ÇÖZÜM: /stockadmin yenile ile manuel test edin
       Konsolu kontrol ederek hata mesajlarını inceleyin

PROBLEM: Ürün satın alınırken para kesilmiyor
ÇÖZÜM: VEC ekonomi komutlarının çalıştığından emin olun
       /vec remove <oyuncu> <miktar> komutunu test edin

PROBLEM: Hediye gönderilmiyor
ÇÖZÜM: Hedef oyuncunun tam ismini yazın (büyük/küçük harf duyarlı)
       Oyuncunun çevrimiçi olduğundan emin olun

PROBLEM: "Internal Error" hatası
ÇÖZÜM: Skript güncel sürümü kullanın
       PlaceholderAPI ve gerekli expansion'lar yüklü olmalı

================================================================================
EK BİLGİLER
================================================================================

Veritabanı Yapısı:
{s::p[sayfa]::slot::[sıra]::item} - Ürün objesi
{s::p[sayfa]::slot::[sıra]::price} - Fiyat
{s::p[sayfa]::slot::[sıra]::stock} - Mevcut stok
{s::p[sayfa]::slot::[sıra]::minstock} - Minimum stok
{s::p[sayfa]::slot::[sıra]::maxstock} - Maximum stok
{s::p[sayfa]::slot::[sıra]::nadirlik} - Nadirlik değeri
{s::time} - Kalan yenileme süresi

Önemli Notlar:
• Sunucu yeniden başlatıldığında stoklar sıfırlanmaz
• Ürünler kalıcı olarak saklanır
• Oyuncu envanteri dolu ise satın alma iptal edilir
• Stok tükendiğinde ürün kırmızı panel ile gösterilir
• Her sayfa bağımsız çalışır

Özelleştirme İpuçları:
• Renk kodlarını değiştirerek tema oluşturabilirsiniz
• Ses efektlerini isteğe göre değiştirebilirsiniz
• Yenileme süresini sunucu ekonomisine göre ayarlayın
• Nadirlik sistemini özel değerlerle genişletebilirsiniz

================================================================================
                              DESTEK VE İLETİŞİM
================================================================================

Bu skript Velthar Wilds tarafından geliştirilmiştir.

Herhangi bir sorun, öneri veya özelleştirme talebi için:
• Sunucu yöneticinize başvurun
• Skript geliştiricisiyle iletişime geçin

Güncellemeler için skript dosyasını düzenli olarak kontrol edin.

================================================================================
                           İYİ OYUNLAR DİLERİZ!
================================================================================
