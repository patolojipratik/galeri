# Bu sistemi kendi arşivinize uyarlama

Bu yöntem başka bir patolog, eğitim grubu veya kurum tarafından kendi anonim sanal slayt arşivi için uyarlanabilir. Patoloji Pratik hesabına bağlanmanız gerekmez ve bağlanmamalısınız.

## Önce karar verin

Kendi kurulumunuz için ayrı değerler kullanın:

- kendi GitHub kullanıcı/organizasyon adınız,
- kendi ana galeri repo adınız,
- kendi `gallery-` benzeri repo önekiniz,
- kendi kaynak slayt klasörünüz,
- kendi güncelleme kanalı adresiniz,
- kendi GitHub tokeniniz,
- kendi güncelleme imzalama anahtarınız.

## 1. Windows bilgisayarını hazırlayın

Gerekli temel bileşenler:

1. Python 3.10 veya daha yeni
2. Git for Windows (veya GitHub Desktop içindeki Git)
3. Yeterli boş disk alanı
4. İnternet bağlantısı
5. Bir GitHub hesabı veya organizasyonu

## 2. Klasörleri oluşturun

Örnek:

```text
E:\Slaytlar
E:\github
```

Sürücü harfi ve klasör adları size ait olabilir. Ancak bir kez belirledikten sonra mümkün olduğunca sabit tutun.

## 3. Program dosyalarını E:\github içine koyun

İlk kurulumdan sonra:

```text
KURULUM.bat
```

çalıştırın. Bu işlem `.venv` sanal Python ortamını ve gerekli paketleri oluşturur.

## 4. Kendi ayarlarınızı yapın

`config/settings.json` içinde kendi değerlerinizi kullanın. Örnek:

```json
{
  "github_username": "KENDI_GITHUB_ADINIZ",
  "gallery_repo": "galeri",
  "repo_prefix": "gallery-",
  "source_dir": "E:\\Slaytlar",
  "work_root": "E:\\github",
  "update_manifest_url": "https://raw.githubusercontent.com/KENDI_GITHUB_ADINIZ/galeri/main/guncelleme/latest.json"
}
```

Patoloji Pratik güncelleme kanalını kendi bağımsız kurulumunuzda kullanmayın; aksi halde bizim sürümlerimiz sizin özelleştirmelerinizi değiştirebilir.

## 5. GitHub tokeni oluşturun

Otomatik repo oluşturma, push, Actions ve Pages yönetimi için GitHub API/token gerekir.

Tokeni mümkün olduğunca yalnızca kendi gerekli repolarınızla sınırlandırın. Uygulamanın kullandığı özelliklere göre şu yetkiler gerekebilir:

- Contents: Read and write
- Workflows: Read and write
- Actions: Read and write
- Pages: Read and write
- Administration: Read and write

Tokeni:

```text
GITHUB_BAGLA.bat
```

ile Windows kimlik kasasına kaydedin. Tokeni repo içine koymayın.

## 6. Kendi güncelleme imzalama anahtarınızı oluşturun

Bağımsız sistem için:

```text
YENI_SISTEM_ANAHTARI_OLUSTUR.bat
```

çalıştırın.

Oluşan **özel anahtarı** çevrimdışı yedekleyin ve asla GitHub'a yüklemeyin. Açık anahtar uygulamayla dağıtılır.

Patoloji Pratik'e ait özel anahtarı başka bir sistemde kullanmayın.

## 7. İlk slaytları ekleyin

Tamamen anonim KFB/SVS veya desteklenen başka WSI dosyalarını kaynak klasörünüze koyun ve:

```text
BASLAT.bat
```

çalıştırın.

Program dönüşüm, repo oluşturma, push, Pages ve ana galeri işlemlerini sırayla yönetir.

## 8. Kendi güncellemenizi yayımlayın

Yeni sürüm ZIP'i hazırlandıktan sonra:

```text
GUNCELLEME_YAYINLA.bat
```

ile kendi `galeri/guncelleme/` kanalınıza yayımlayın.

## 9. Yapay zekâ ile kurulum

ChatGPT, Codex, Claude, Gemini veya benzeri bir araçtan yardım alıyorsanız araca önce repo kökündeki:

```text
AGENTS.md
```

dosyasını okumasını söyleyin. Bu dosya hangi verilerin korunacağını, hangi yolların değiştirilebileceğini ve kurulum/kurtarma sırasını yapay zekâ için açık biçimde tanımlar.

## 10. Hasta verisi yayımlamayın

Etiket görselleri ve metadata dahil her şeyi yayımlamadan önce anonimleştirin. Herkese açık GitHub reposuna hasta adı, protokol numarası veya başka tanımlayıcı bilgi koymayın.

## 11. Lisans

Bu yöntemi başkalarının açıkça kopyalayıp değiştirmesine izin vermek istiyorsanız kendi reponuza uygun bir açık kaynak `LICENSE` dosyası ekleyin. Lisans seçimi proje sahibinin kararıdır.
