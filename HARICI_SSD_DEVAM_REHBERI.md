# Harici SSD ile devam etme, yeni bilgisayara taşıma ve kurtarma

Bu belge teknik bilgisi az olan bir kullanıcının hazırlanmış Patoloji Pratik SSD'sini güvenli biçimde kullanabilmesi içindir.

## En kısa kullanım

SSD mevcut bilgisayarda düzgün çalışıyorsa:

1. SSD'yi bağlayın.
2. `E:\github\BASLAT.bat` dosyasına çift tıklayın.
3. Güncelleme önerilirse ekrandaki seçeneği kullanın.
4. Program açıldığında normal çalışmaya devam edin.
5. **GÜVENLE KAPATABİLİRSİNİZ** yazısını görmeden SSD'yi çıkarmayın veya bilgisayarı kapatmayın.

---

## A. SSD'yi başka bir Windows bilgisayara taktım

### 1. Önce sürücü harfine bakın

Dosya Gezgini'ni açın. SSD mümkünse **E:** olmalıdır.

Beklenen klasörler:

```text
E:\github
E:\Pratik_slaytları
```

SSD zaten `E:` ise sonraki adıma geçin.

### 2. SSD E: değilse

**En güvenli ve kolay çözüm SSD'nin harfini E: yapmaktır.**

Windows'ta:

1. Başlat düğmesine sağ tıklayın.
2. **Disk Yönetimi** açın.
3. Harici SSD'yi boyutundan ve adından doğrulayın.
4. SSD bölümüne sağ tıklayın.
5. **Sürücü Harfi ve Yollarını Değiştir** seçeneğini açın.
6. Mümkünse `E:` harfini atayın.

`E:` başka bir cihaz tarafından kullanılıyorsa önce o cihazın harfini başka bir boş harfe taşıyabilirsiniz.

> Yanlış diskin sürücü harfini değiştirmeyin. Emin değilseniz işlem yapmadan yardım alın.

### 3. Python kurulumu

Yeni bilgisayarda Python yoksa **Python 3.10 veya daha yeni** bir Python 3 sürümü kurun.

Kurulum sırasında mümkünse:

```text
Add python.exe to PATH
```

seçeneğini işaretleyin.

### 4. Git kurulumu

Program yayınlama sırasında `git.exe` kullanır. Yeni bilgisayarda **Git for Windows** kurulması en basit çözümdür. GitHub Desktop zaten kuruluysa program onunla gelen Git'i de bulabilir.

### 5. Eski sanal Python ortamını yenileyin

`.venv` başka bilgisayardan taşındığında eski Python yolunu içerebilir. Bu klasörde kullanıcı verisi yoktur.

Program kapalıyken:

```text
E:\github\.venv
```

klasörünün adını örneğin:

```text
.venv_eski
```

olarak değiştirin.

Ardından:

```text
E:\github\KURULUM.bat
```

çalıştırın. Program yeni bilgisayara uygun `.venv` klasörünü ve gerekli Python paketlerini oluşturur.

Kurulum tamamlandıktan sonra:

```text
E:\github\BASLAT.bat
```

çalıştırın.

### 6. GitHub bağlantısı

Yeni Windows bilgisayarında daha önce kaydedilmiş GitHub tokeni bulunmayabilir.

Sadece yayınlama yapılacaksa ve token eksik uyarısı alınırsa hesap sahibi:

```text
E:\github\GITHUB_BAGLA.bat
```

ile yeni bilgisayara tokeni güvenli biçimde kaydeder.

GitHub hesabının şifresini SSD'yi kullanan kişiye vermek gerekmez. Tokeni düz metin dosyasına, e-postaya, mesajlaşma uygulamasına veya ekran görüntüsüne koymayın.

---

## B. SSD E: yapılamıyor

Bu sistem uzun süredir `E:` yollarıyla kullanılmışsa yalnızca `settings.json` değiştirmek yeterli olmayabilir; `slides.csv` içinde de eski mutlak kaynak yolları bulunabilir.

Bu nedenle **öncelik SSD'yi E: yapmak olmalıdır.**

E: kullanmak gerçekten mümkün değilse:

1. `data\slides.csv` dosyasını ayrıca yedekleyin.
2. `config\settings.json` içindeki kaynak/çalışma yollarını yeni harfe taşıyın.
3. `data\slides.csv` içinde eski `E:\` yolları olup olmadığını kontrol edin.
4. Yalnızca yol alanlarını yeni harfe taşıyın; tanı, başlık ve diğer metadata alanlarını değiştirmeyin.
5. CSV dosyasını elle düzenleyecekseniz biçimi bozmamak için çok dikkatli olun.

Bu durumda bir yapay zekâ veya teknik destek kullanıyorsanız ona repodaki `AGENTS.md` dosyasını okutun.

---

## C. SSD bozuldu ama başka bilgisayarda devam etmek istiyorum

### Elinizde SSD'nin yedeği varsa

Yeni bir SSD hazırlayın ve mümkünse `E:` harfini verin.

Aşağıdakileri geri yükleyin:

```text
E:\github
E:\Pratik_slaytları
```

Özellikle önemli olanlar:

```text
E:\github\data\slides.csv
E:\github\config\settings.json
E:\Pratik_slaytları\   (kaynak KFB/SVS dosyaları)
```

Ardından yeni bilgisayarda:

1. Python 3.10+ kurun.
2. Git for Windows kurun.
3. Eski `.venv` klasörünü yeniden kullanmayın; yeniden oluşturun.
4. `KURULUM.bat` çalıştırın.
5. Gerekiyorsa `GITHUB_BAGLA.bat` ile tokeni kaydedin.
6. `BASLAT.bat` çalıştırın.

### SSD tamamen kayıp ve yerel yedek yoksa

GitHub'da daha önce yayımlanmış slaytlar ve ana galeri web üzerinde kalabilir. Ancak GitHub deposu bilinçli olarak yerel `data/slides.csv`, token, özel anahtar ve kaynak KFB/SVS dosyalarının tam yedeği değildir.

Bu nedenle yeni slayt eklemeye ve eksik işlemleri güvenli biçimde sürdürmeye başlamadan önce eldeki yedekleri kontrol edin.

`slides.csv` yoksa bazı yayın bilgileri ana galerideki `slides.json` ve `gallery-XXX` depolarından yeniden oluşturulabilir; fakat bu bir **kurtarma işlemi** olarak ele alınmalı, doğrudan boş bir `slides.csv` ile devam edilmemelidir.

---

## D. Normal kullanım düğmeleri

- **Sıradaki 1 Slaytı İşle:** yalnızca sıradaki slaytı işler.
- **Tümünü İşle:** bekleyen bütün slaytları sırayla işler.
- **Mevcut Slaytı Bitir ve Dur:** aktif slaytı güvenli noktaya kadar tamamlar, sonra yeni slayta başlamaz.
- **Slayt bilgilerini düzenle:** başlık, organ, tanı, açıklama ve etiketleri düzenler.
- **Ana galeriyi yayımla:** merkezi galeri dosyalarını gönderir.
- **Yayınları şimdi kontrol et:** web yayını henüz doğrulanmamış kayıtları denetler.

Geçici GitHub Actions veya Pages hatasını **kötü yükleme** olarak değerlendirmeyin.

---

## E. Yeni slayt ekleme

Anonim kaynak dosyaları şu klasöre kopyalayın:

```text
E:\Pratik_slaytları
```

Sonra `BASLAT.bat` açın. Program yeni dosyaları otomatik bulur.

---

## F. Yedekleme

En az şu dosyanın düzenli başka bir kopyasını tutun:

```text
E:\github\data\slides.csv
```

Ayrıca kaynak KFB/SVS dosyalarının tek kopyası yalnızca bu SSD üzerinde olmamalıdır.

Bakım bilgisayarındaki güncelleme **özel imzalama anahtarı** da ayrı ve güvenli bir yerde yedeklenmelidir; bu anahtar kullanıcıya verilen SSD'ye veya GitHub'a konulmamalıdır.
