# Harici SSD ile devam etme rehberi

Bu rehber, hazırlanmış Patoloji Pratik harici SSD'sini başka bir bilgisayarda güvenli biçimde kullanmak veya kaldığı yerden devam ettirmek içindir.

## En kısa kullanım

1. SSD'yi bilgisayara bağlayın.
2. SSD `E:` olarak görünüyorsa doğrudan:

```text
E:\github\BASLAT.bat
```

çalıştırın.
3. Güncelleme varsa program size sorar; kabul edin.
4. Yeni KFB/SVS slaytları `E:\Pratik_slaytları` klasörüne koyun.
5. **Tümünü İşle** veya **Sıradaki 1 Slaytı İşle** ile devam edin.
6. Bilgisayarı kapatmadan/SSD'yi çıkarmadan önce **GÜVENLE KAPATABİLİRSİNİZ** yazısını bekleyin.

## SSD E: değilse

Windows bazen diske `F:`, `G:` gibi başka harf verir. En kolay yöntem Disk Yönetimi'nden bu harfi `E:` yapmaktır.

Bunu yapmak istemiyorsanız `E:\github\config\settings.json` içindeki `source_dir` ve `work_root` yollarını yeni disk harfine göre değiştirmek gerekir. Bu işi bir yapay zekâ ile yapacaksanız repodaki `AGENTS.md` dosyasını önce okutun.

## Yeni bilgisayarda Python/Git yoksa

Önce Python 3.10 veya daha yeni bir 64-bit Python ve Git for Windows kurun. Sonra SSD'deki:

```text
E:\github\KURULUM.bat
```

varsa onu çalıştırın; yoksa `BASLAT.bat` ile başlayın ve ekrandaki eksik bileşen uyarılarını izleyin.

`.venv` klasörü başka Windows bilgisayara taşındığında her zaman güvenilir değildir. Sorun olursa `.venv` yeniden oluşturulabilir; `data`, `config`, kaynak slaytlar ve yayınlanmış repolar silinmemelidir.

## Güncelleme

### Normal çevrimiçi güncelleme

Sadece `BASLAT.bat` çalıştırın. Program GitHub'daki:

```text
patolojipratik/galeri/guncelleme/latest.json
```

dosyasını kontrol eder ve yeni sürüm varsa teklif eder.

### Size ZIP olarak verilen güncelleme

ZIP + `.sha256.txt` + `.sig` dosyalarını açmadan:

```text
E:\github\guncelleme
```

klasörüne koyun ve `BASLAT.bat` çalıştırın.

3.7.2 ve sonrasında, bu bilgisayarda `patolojipratik` için geçerli yayın tokeni bulunuyorsa, başarıyla kurulan yerel güncelleme aynı zamanda ana GitHub reposundaki `guncelleme/` kanalına otomatik eşitlenir. Bu eşitleme başarısız olursa program yine çalışır; manuel tekrar için `GUNCELLEME_KANALINI_ESITLE.bat` kullanılabilir.

## Slayt bilgileri: Başlık, Tanı ve Organ

Masaüstünde **Slayt bilgilerini düzenle** penceresinde:

- **Başlık:** web kartında büyük ve kalın görünen kısa başlık.
- **Tanı:** başlıktan farklıysa web kartında ikinci satırda görünen daha ayrıntılı tanı.
- **Organ / sistem:** üçüncü satırda görülür.
- **Açıklama:** ayrıntı penceresinde gösterilir.
- **Etiketler:** arama ve ayrıntı için kullanılır.

3.7.2 ile web kartlarının sırası **Başlık → Tanı → Organ / sistem** olarak standartlaştırılmıştır.

## Ana galeri bilgilerini yayımlama

Bilgi değişikliğinden sonra **Kaydet ve İnternette Yayınla** veya ana penceredeki **Ana galeriyi yayımla** kullanılabilir. `README.md` ve `SCREEN.PNG` normal galeri yayını sırasında korunur.

## Web görüntüsü açılmıyorsa

Önce programdaki **Web görüntülerini onar** düğmesini veya:

```text
E:\github\WEB_GORUNTU_ONAR.bat
```

kullanın. Ardından GitHub Actions tamamlandıktan sonra:

```text
E:\github\WEB_GORUNTU_KONTROL.bat
```

ile kontrol edin.

Geçici Pages/Actions hatasında **Kötü Yüklemeyi Tamamen Kaldır** kullanmayın.

## GitHub bağlantısı

Normal kullanımda tekrar giriş gerekmez. Token geçersizse:

```text
E:\github\GITHUB_BAGLA.bat
```

çalıştırılır. GitHub hesap şifresi SSD'yi kullanan kişiye verilmemelidir. Tokeni sohbet, ekran görüntüsü veya metin dosyasına yazmayın.

## SSD veya bilgisayar bozulursa

En değerli yerel dosyalar:

```text
E:\github\data\slides.csv
E:\github\config\settings.json
```

ve kaynak KFB/SVS arşividir. Bunların ayrı yedeğini tutun. GitHub'a daha önce yüklenmiş `gallery-XXX` repolarını kurtarma amacıyla silmeyin.

## Yapılmaması gerekenler

- İşlem sürerken SSD'yi çıkarmayın.
- Aynı anda iki Slayt Yayıncısı açmayın.
- `data`, `config`, `repos`, `work` klasörlerini rastgele silmeyin.
- Geçici GitHub hatasını kötü slayt sanıp repo silmeyin.
- Token veya özel imzalama anahtarını GitHub'a yüklemeyin.
