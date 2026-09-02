# RedMagic AW22XXX RGB Control Center

RedMagic 11 Pro için **KernelSU tabanlı** kapsamlı RGB kontrol merkezi.  
Logo, omuz tetikleri ve soğutma fanı LED'lerini tek merkezden yönetin; GameSpace tuşunu yeniden yönlendirin ve sıvı soğutma pompasını LED'lerle senkronize edin.

## Neden Bu Modül?

RedMagic cihazlarının donanımı RGB efektlerini destekler, ancak yazılım sınırlıdır. Bu modül, **AW22XXX LED sürücüsüne** doğrudan erişerek donanımın tüm potansiyelini ortaya çıkarır:

- 🎨 **Üç bölgeyi senkronize et:** Logo, tetik ve fan LED'leri aynı anda döngüsel renk değiştirir.
- ⚡ **Bölge başına bağımsız kontrol:** Her bölge için ayrı renk paleti ve efekt modu.
- 🎮 **GameSpace tuşunu yönlendir:** Donanım anahtarını istediğiniz uygulamayı açacak şekilde ayarlayın.
- ❄️ **Sıvı soğutma pompası senkronizasyonu:** LED'ler açıkken pompa otomatik çalışır, tam kapanmada durur.
- 💾 **Kalıcı ayarlar:** Tüm yapılandırma `/data/adb/` altında saklanır, yeniden başlatmada korunur.

## Özellikler

- **Senkronize RGB döngüsü** – Üç bölge arasında akıcı renk geçişi
- **Bağımsız bölge ayarları**:
  - Logo & Tetik: 8 standart renk
  - Fan: 8 standart + 8 genişletilmiş renk (toplam 16)
- **Zengin efekt modları**:
  - Logo / Tetik: Sabit, Nefes, Yanıp Sönme, Hızlı Yanıp Sönme
  - Fan: Sabit, Nefes, Yanıp Sönme, Hızlı Yanıp Sönme, Sürekli Parlama
- **GameSpace tuş yönlendirme**:
  - Fiziksel GameSpace anahtarını algılar
  - GameSpace'i kapatıp seçilen uygulamayı başlatır
  - Hedef uygulama WebUI üzerinden elle girilebilir veya listeden seçilebilir
- **Sıvı soğutma pompası kontrolü**:
  - LED'ler aktifken pompa otomatik açılır
  - Geçici LED kapanmalarında fan ile birlikte pompa da toparlanır
  - Tüm LED'ler kapandığında pompa da tamamen durur
- **Müzik farkındalığı** – Medya oynatılırken LED'ler kapanmaz
- **Oyun LED algılama** – Oyun kontrollü omuz LED'leri serbest kaldığında normal davranışa döner
- **Akıllı kapanma** – Üç bölge de kapanma sinyali aldığında LED'ler kapanır
- **Wakelock yönetimi** – Yalnızca LED'ler aktifken wakelock tutulur
- **Dinamik yapılandırma** – Ayarlar her 10 döngüde yeniden okunur, script yeniden başlatma gerektirmez
- **Performans optimizasyonu** – Birincil sysfs yolu ile otomatik yedekleme, `-10` işlem önceliği

## Ekran Görüntüleri

### Ana Arayüz

![Ana Arayüz 1](Screenshot_20260901_142527.jpg)

![Ana Arayüz 2](Screenshot_20260901_142535.jpg)

![Ana Arayüz 3](Screenshot_20260901_142544.jpg)

### RGB Renkler

![RGB Efekt 1](Screenshot_20260901_142547.jpg)

![RGB Efekt 2](Screenshot_20260901_142549.jpg)

### RGB Efektler

![GameSpace 1](Screenshot_20260901_142553.jpg)

![GameSpace 2](Screenshot_20260901_142555.jpg)

![GameSpace 3](Screenshot_20260901_142559.jpg)

## Kurulum

1. ZIP dosyasını indirin.
2. **KernelSU** uygulamasını açın.
3. **Modüller** sekmesine gidin.
4. **Yükle**'ye dokunun ve ZIP dosyasını seçin.
5. Cihazınızı **yeniden başlatın**.
6. KernelSU → Modüller → **RedMagic RGB Control Center** üzerine dokunarak WebUI'yi açın.

## WebUI Kullanımı

WebUI arayüzü şunları içerir:

- Mod seçici (Döngü / Sabit)
- Hız kaydırıcısı (0.1 sn – 6.0 sn)
- Her bölge için canlı önizleme daireleri
- Bölge sekmeleri:
  - Efekt modu açılır menüsü
  - Aktif / pasif renk çipleri
  - Akıllı karıştır, rastgele karıştır, sıfırla, kaydet butonları
  - Sabit renk seçimi
- GameSpace yönlendirme bölümü:
  - Hedef uygulama paket adını elle girme
  - Yüklü uygulama listesini yükleme (aranabilir)
  - Hedef uygulamayı seçme (`/data/adb/gamespace_target.txt` içinde saklanır)


## Uyumluluk

**ÖNEMLİ:** Bu modül yalnızca **RedMagic 11 Pro** üzerinde test edilmiştir.

- Diğer RedMagic modelleri veya farklı marka cihazlarda **test edilmemiştir**.
- Donanım yolları ve LED sürücüleri nesillere göre farklılık gösterebilir; uyumluluk bilinmemektedir.

## Uyarı ve Sorumluluk Reddi

**KULLANIM RİSKİ SİZE AİTTİR.**

- Bu modül, düşük seviyeli kernel sysfs düğümleri ve donanım denetleyicileriyle doğrudan etkileşime girer.
- Kurulum ve kullanım sonucunda donanım hasarı, yazılım bozulması, sistem kararsızlığı veya LED arızası meydana gelebilir.
- Geliştirici hiçbir zarardan sorumlu tutulamaz.
- Bu proje yalnızca **eğitim ve araştırma amaçlıdır**, kötüye kullanım için tasarlanmamıştır.

**Yüklemeden önce mutlaka yedek alın.**
