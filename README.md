

# Tedarik İade Projesi - HGD (Hızlı Geri Dönüşüm)

[cite_start]Bu proje, Yıldız Holding Hızlı Geri Dönüşüm (HGD) depo alanlarında gerçekleştirilen ürün takibi ve iade süreçlerinin RFID teknolojisi ile otomatize edilmesini, verilerin MOBİS NG ve SAP sistemleri ile entegre bir şekilde yönetilmesini sağlar[cite: 5, 6].

## 📖 İçindekiler

  - [Proje Hakkında](https://www.google.com/search?q=%23proje-hakk%C4%B1nda)
  - [İş Akışı ve Kapsam](https://www.google.com/search?q=%23i%C5%9F-ak%C4%B1%C5%9F%C4%B1-ve-kapsam)
  - [Sistem Mimarisi ve Entegrasyon](https://www.google.com/search?q=%23sistem-mimarisi-ve-entegrasyon)
  - [Donanım Gereksinimleri](https://www.google.com/search?q=%23donan%C4%B1m-gereksinimleri)
  - [Teknik ve Güvenlik Gereksinimleri](https://www.google.com/search?q=%23teknik-ve-g%C3%BCvenlik-gereksinimleri)
  - [Test ve Devreye Alma](https://www.google.com/search?q=%23test-ve-devreye-alma)

-----

## 🚀 Proje Hakkında

Tedarik İade Projesi, bayilerden iade edilen ürünlerin çuval bazında takibini ve doğrulanmasını sağlar. [cite_start]Süreç, sahadan toplanan kimlik/ID verilerinin RFID donanımları ile işlenmesi ve merkezi sistemlerle (SAP/MOBİS NG) senkronize edilmesi üzerine kuruludur[cite: 6].

**Temel Hedefler:**

  * [cite_start]İade süreçlerinin RFID ile otomatize edilmesi[cite: 26].
  * [cite_start]Manuel sayım hatalarının önüne geçilmesi ve %100 doğrulukla okuma sağlanması[cite: 126].
  * [cite_start]Anlık stok ve iade takibi entegrasyonu[cite: 25].

-----

## 🔄 İş Akışı ve Kapsam

Proje, sahadan başlayıp HGD depolarında sonlanan bir veri akışını kapsar.

1.  [cite_start]**Saha Operasyonu:** Saha sayım ekipleri, iade ürün çuvallarını mobil yazıcılar ve el terminalleri kullanarak barkodlu RFID etiketlerle işaretler[cite: 20, 22].
2.  [cite_start]**Veri Kaydı:** Etiketlenen çuvallar MOBIS NG üzerinden kabul edilir ve SAP sistemine kayıt atılır[cite: 23].
3.  [cite_start]**HGD Depo Kabulü:** Nakliye araçları depoya ulaştığında, RFID Tünel sistemi araç içerisindeki çuvalları okur[cite: 25].
4.  [cite_start]**Doğrulama:** Okunan ID'ler SAP'den çekilen verilerle anlık olarak karşılaştırılır ve sayım/kabul işlemi tamamlanır[cite: 25].

-----

## 🛠 Sistem Mimarisi ve Entegrasyon

Sistem, TCP/IP tabanlı endüstriyel haberleşme protokolleri üzerinde çalışır ve aşağıdaki entegrasyonları destekler:

  * [cite_start]**Haberleşme Protokolleri:** MQTT, OPC UA veya Modbus-TCP tercih edilmektedir[cite: 119].
  * [cite_start]**Entegrasyon:** SAP ve MOBIS NG sistemleri ile API üzerinden tam entegrasyon sağlanmalıdır[cite: 133].
  * [cite_start]**Yazılım Katmanı:** RFID donanımları, dahili veya harici bir ara katman yazılımı (Middleware) üzerinden yönetilebilir ve konfigüre edilebilir olmalıdır[cite: 122].

### RFID Tünel Yazılımı Akışı

  * [cite_start]SAP'den araç ve çuval ID bilgilerini çeker[cite: 137].
  * [cite_start]Sensör tetiklemesi ile okumayı başlatır ve bitirir[cite: 138, 141].
  * [cite_start]Verileri lokal veritabanına kaydeder, onay sonrası SAP'ye aktarır[cite: 142].
  * [cite_start]Offline durumlarda veriyi saklar, bağlantı geldiğinde senkronize eder[cite: 144].

-----

## 🖥 Donanım Gereksinimleri

[cite_start]Proje kapsamında kullanılan temel donanım bileşenleri aşağıdadır[cite: 29, 31, 32, 34]:

| Bileşen | Özellikler | Adet |
| :--- | :--- | :--- |
| **El Terminali** | Android/IOS, 5G, WIFI6, 6", Zebra/Honeywell muadili | 20 |
| **Mobil Yazıcı** | Outdoor, DT, BT, Label Sensor, TCP/IP destekli | 16 |
| **RFID Tünel Sistemi** | 45x90/90x90 Sigma profil, Pnömatik kapaklar, PLC, Işık/Ses ikazı | 1 |
| **Fixed RFID Reader** | 8-Port, PoE, EMEA 800MHz | 2 |
| **Panel PC** | Windows İşletim Sistemli Endüstriyel PC | 1 |

-----

## 🔒 Teknik ve Güvenlik Gereksinimleri

Geliştirilen yazılım ve donanım konfigürasyonları Yıldız Holding güvenlik standartlarına tam uyum sağlamalıdır.

### Güvenlik Standartları

  * [cite_start]**Kimlik Doğrulama:** SSO entegrasyonu ve dış erişimlerde Çift Faktörlü Kimlik Doğrulama (2FA) zorunludur[cite: 191, 195].
  * [cite_start]**Şifreleme:** Tüm veri alışverişi ve kullanıcı kimlik bilgileri şifreli olarak iletilmelidir[cite: 192, 221].
  * [cite_start]**Loglama:** Başarılı/başarısız tüm erişim ve işlemler 5 yıl süreyle Qradar uyumlu formatta loglanmalıdır[cite: 207, 212].
  * [cite_start]**Zafiyet Yönetimi:** Güvensiz protokoller (TELNET, FTP, HTTP vb.) kullanılmamalı, kullanılmayan portlar kapatılmalıdır[cite: 188, 189].

### Geliştirme Standartları

  * [cite_start]Versiyon kontrolü için Holding TFS sistemi kullanılmalıdır[cite: 214].
  * [cite_start]Üretim ortamı haricinde Geliştirme ve Test ortamları bulunmalıdır[cite: 213].
  * [cite_start]Uygulama kodları, canlıya alınmadan önce güvenlik testlerinden geçirilmelidir[cite: 224].

-----

## 🧪 Test ve Devreye Alma

[cite_start]Projenin kabulü için aşağıdaki test aşamaları tamamlanmalıdır[cite: 163]:

1.  [cite_start]**Unit Testler:** Geliştirilen ekran ve fonksiyonların birim testleri[cite: 164].
2.  [cite_start]**Entegrasyon Testi:** SAP/MOBIS NG veri akışının doğrulanması[cite: 58].
3.  [cite_start]**Sinyalizasyon Testi:** RFID okuma performansının doğrulanması[cite: 57].
4.  [cite_start]**Kullanıcı Kabul Testleri (UAT):** Raporların ve sahadaki fiili sayımların doğruluğunun teyidi[cite: 165, 167].

-----

## 📜 Lisans ve Gizlilik

Bu projedeki tüm teknik detaylar, veri ve belgeler **Yıldız Holding** mülkiyetindedir. [cite_start]İzinsiz kopyalanamaz, çoğaltılamaz ve üçüncü şahıslarla paylaşılamaz[cite: 8, 9].
