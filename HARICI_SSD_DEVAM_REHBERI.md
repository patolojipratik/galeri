# Harici SSD ile devam etme, evden çalışma, bakım, yedekleme ve kurtarma

Bu rehber, hazırlanmış Patoloji Pratik harici SSD'sini günlük kullanmak, başka bilgisayara taşımak, evden devam etmek ve **Bakım ve sistem** ekranını doğru kullanmak içindir.

## En kısa kullanım

1. Harici SSD'yi bilgisayara bağlayın.
2. SSD içindeki `github\BASLAT.bat` dosyasına çift tıklayın.
3. Program kaynak slayt klasörünü bulamazsa doğru klasörü seçin.
4. Slaytları normal şekilde işleyin/yayımlayın.
5. SSD'yi çıkarmadan veya bilgisayarı kapatmadan önce **GÜVENLE KAPATABİLİRSİNİZ** yazısını bekleyin.

Teknik `.py` veya `.bat` dosyalarını günlük kullanımda elle açmanız gerekmez.

## Evden devam edebilir miyim?

**Evet.** Aynı harici SSD'yi iş yerinden eve götürüp başka bir Windows bilgisayarda kaldığınız yerden devam edebilirsiniz.

Örnek:

```text
İş bilgisayarı: SSD = E:
Ev bilgisayarı:  SSD = F:
```

Bu sorun değildir. Yeni sistem `BASLAT.bat` dosyasının bulunduğu sürücüyü algılar ve program kökünü ona göre kullanır.

### Ev bilgisayarında yapılacaklar

1. SSD'yi bağlayın.
2. `F:\github\BASLAT.bat` gibi, SSD'nin aldığı harfteki BASLAT'ı çalıştırın.
3. Kaynak KFB/SVS klasörü aynı SSD'deyse program onu bulmaya çalışır.
4. Bulamazsa size klasör seçtirir ve uygun konumu kaydeder.
5. Python veya Git eksikse ilk kullanım kontrolü devreye girer.

### GitHub yayını evden yapılabilir mi?

Evet. Fakat GitHub tokeni **SSD üzerinde taşınmaz**. Güvenlik nedeniyle Windows kimlik kasasında tutulur.

Bu nedenle ev bilgisayarında daha önce GitHub bağlantısı kurulmadıysa, yeni slayt/repo/ana galeri yayımlamak için bir kez GitHub bağlantısı yapılması gerekir.

Tokeni:

- sohbet mesajına,
- WhatsApp'a,
- ekran görüntüsüne,
- düz metin dosyasına

yazmayın.

### Aynı anda iki bilgisayardan yayın yapmayın

Aynı galeri üzerinde iş ve ev bilgisayarından aynı anda yayın başlatmayın. Bir bilgisayardaki işlem tamamlanıp **GÜVENLE KAPATABİLİRSİNİZ** durumuna geldikten sonra SSD'yi diğer bilgisayara taşıyın.

## Önerilen SSD düzeni

```text
Harici SSD
├── github
└── Pratik_slaytları
```

Bu düzenin avantajı, program ve o gün işlenecek kaynak slaytların birlikte taşınabilmesidir.

Orijinal KFB/SVS arşivinin tek kopyasını çalışma SSD'sinde tutmayın; uzun dönem için ayrıca arşiv diski kullanın.

# Bakım ve sistem

Ana programdaki **Bakım ve sistem** düğmesi günlük slayt işlemlerinden ayrı teknik/bakım merkezidir.

## Sistem sağlık kontrolü

Kontrol ettiği başlıca alanlar:

- Python çalışma ortamı,
- Git kurulumu,
- GitHub bağlantısı/yayın yetkisi,
- `slides.csv`,
- kaynak slayt klasörü,
- disk boş alanı,
- ana galeri erişimi,
- güncelleme kanalı,
- kritik klasörler.

**Ne işe yarar?** Bir sorun olduğunda hangi parçanın eksik olduğunu hızlıca gösterir.

**Ne yapmaz?** Kaynak slaytları veya GitHub repolarını silmez; sağlık kontrolü tek başına büyük onarım yapmaz.

## Konumlar ve ilk kurulum

Buradan programın kullandığı temel konumları görebilir/değiştirebilirsiniz:

- kaynak slayt klasörü,
- çalışma alanı,
- bilgisayardaki güvenlik yedeği klasörü.

SSD başka sürücü harfi aldığında veya kaynak slaytlar başka diske taşındığında kullanılır.

## Şimdi yedekle / Güvenlik yedeği

Küçük fakat kritik yerel bilgilerin ek kopyasını oluşturur:

- `slides.csv`,
- temel ayarlar,
- konum bilgileri,
- sürüm bilgileri.

**Kaynak KFB/SVS dosyalarını kopyalamaz.**  
**GitHub tokenini yedeklemez.**

Varsayılan PC yedek alanı genellikle:

```text
Belgeler\PatolojiPratik_Yedek
```

Ayrıca uygun olduğunda SSD içindeki `_arsiv\kurtarma` alanında küçük bir kopya tutulabilir.

### PC + SSD yedeği neden iki yerde?

Amaç küçük kritik veriyi tek fiziksel diske bağımlı bırakmamaktır.

Önerilen güvenlik katmanları:

```text
Harici SSD                 çalışan program / günlük çalışma
PC Belgeler                küçük kritik güvenlik yedeği
GitHub                     yayımlanmış galeri ve sanal mikroskoplar
Ayrı arşiv HDD/SSD          orijinal KFB/SVS uzun dönem arşivi
```

## Kurtarma ZIP'i oluştur

Yeni SSD veya yeni bilgisayar sonrası sistemi yeniden ayağa kaldırmayı kolaylaştıran küçük kurtarma paketi üretir.

Kurtarma ZIP'i:

- kritik ayarları ve envanteri içerebilir,
- GitHub tokenini içermez,
- kaynak KFB/SVS dosyalarını içermez.

### Güvenlik yedeği ile farkı

- **Güvenlik yedeği:** sık alınan küçük kritik veri kopyasıdır.
- **Kurtarma ZIP'i:** arıza sonrası yeniden kurulum için daha bütünlüklü başvuru paketidir.

Kurtarma ZIP'inin bir kopyasını farklı fiziksel diskte saklamak faydalıdır.

## Web görüntülerini kontrol et

Yayımlanmış slaytların gerçekten webden okunup okunamadığını kontrol eder. Yalnızca GitHub'da dosya var mı sorusuna bakmakla kalmaz; mümkün olduğunda:

- Pages sayfasını,
- `slide.dzi` dosyasını,
- örnek görüntü tile'larını

kontrol eder.

**Kontrol işlemi slayt silmez.**

## Web görüntülerini onar

Pages/viewer tarafında sorun bulunan yayınları düzeltmek için kullanılır. Örneğin sayfa açılıyor fakat görüntü gelmiyorsa kullanılabilir.

Geçici GitHub/Pages hatasını otomatik olarak "kötü slayt" kabul edip kaynak dosyayı silmez.

## Güncelleme kanalını eşitle

Yerelde başarıyla kurulmuş son program güncellemesini GitHub'daki resmi güncelleme alanına yollar:

```text
patolojipratik/galeri/guncelleme/
```

Güncel sürümde birlikte bulunması gereken dosyalar:

```text
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sha256.txt
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sig
latest.json
SURUM_NOTLARI.md
```

Güncellemeyi **görmek ve indirmek** için GitHub tokeni gerekmez. Güncellemeyi GitHub'a **yayımlamak** için yazma yetkili token gerekir.

## Yerel temizlik önizleme

Nelerin temizlenebileceğini önce listeler. **Önizleme tek başına dosya silmez.**

Eski test raporları, eski sürüm belgeleri ve gereksiz geçici dosyalar için kullanılır.

## Kök klasörü sadeleştir

Kullanıcının günlük olarak görmesine gerek olmayan teknik/eski dosyaları düzenler:

```text
_sistem    teknik araçlar
_belgeler  güncel belgeler
_arsiv     eski dosyalar / geçmiş sürümler
```

Kritik `data`, `config`, `repos`, `work`, `guncelleme` ve kaynak slaytlar rastgele silinmez.

## Eski logları temizle

`logs\app.log` zamanla büyüyebilir. Loglar hata incelemesi için değerlidir; birkaç MB olması tek başına problem değildir.

Yeni sistem `app.log` belirlenen sınırı geçtiğinde eski logları döndürerek sınırlı sayıda geçmiş log tutabilir. Bakım ekranından durum görülebilir ve eski log temizliği istenebilir.

Aktif log dosyası kullanım sırasında zorla silinmez.

## Rehberler

**Rehberler** düğmesi GitHub'daki `REHBERLER.md` dokümantasyon menüsünü açar. Kurulum, güncelleme, yönetim ve kendi sistemini kurma belgelerine buradan ulaşabilirsiniz.

# Arıza ve kurtarma

## Bilgisayar bozuldu, SSD sağlam

1. SSD'yi başka Windows bilgisayara bağlayın.
2. `github\BASLAT.bat` çalıştırın.
3. Gerekirse Python/Git yeniden hazırlanır.
4. Kaynak klasör istenirse seçin.
5. GitHub'a yayın yapacaksanız yeni bilgisayarda GitHub bağlantısını bir kez kurun.

## SSD bozuldu, web yayınları çalışıyor

GitHub'da yayımlanmış sanal mikroskoplar SSD'den bağımsız olarak çalışmaya devam eder.

Yeni SSD'ye program yeniden kurulabilir; PC güvenlik yedeği ve kurtarma ZIP'i yerel envanter/ayarların geri kazanılmasını kolaylaştırır.

Ancak GitHub'daki DZI/JPEG tile'ları **orijinal SVS/KFB dosyasının birebir arşiv yedeği değildir**. Orijinal tarama dosyalarını ayrıca saklayın.

## Kaynak `Pratik_slaytları` klasörünü boşaltabilir miyim?

Yayını tamamlanmış slaytların webde çalışması için orijinal KFB/SVS dosyasının çalışma klasöründe kalması gerekmez.

Bu nedenle tamamlanmış kaynakları **ayrı güvenli arşiv diske taşıdıktan sonra** çalışma klasörünü boşaltabilirsiniz. Yeni slayt geldikçe yalnızca yeni dosyaları buraya koyabilirsiniz.

Orijinal dosyaları tamamen silmek önerilmez.

# Yapılmaması gerekenler

- İşlem sürerken SSD'yi çıkarmayın.
- Aynı SSD ile iki bilgisayarda aynı anda yayın yapmayın.
- `data`, `config`, `repos`, `work` klasörlerini rastgele silmeyin.
- Geçici GitHub/Pages hatasını kötü slayt sanıp repo silmeyin.
- GitHub tokenini veya özel imzalama anahtarını repoya yüklemeyin.
- Kaynak KFB/SVS'nin tek kopyasını çalışma SSD'sinde bırakmayın.
- **GÜVENLE KAPATABİLİRSİNİZ** yazısını görmeden SSD'yi ayırmayın.

# Evden çalışma — 30 saniyelik özet

```text
SSD'yi eve götür
→ ev PC'sine bağla
→ github\BASLAT.bat
→ kaynak klasör bulunamazsa seç
→ bu PC'den ilk GitHub yayını ise GitHub bağlantısını kur
→ normal çalış
→ GÜVENLE KAPATABİLİRSİNİZ
→ programı kapat ve SSD'yi güvenli çıkar
```

Daha fazla belge için: **[REHBERLER.md](REHBERLER.md)**
