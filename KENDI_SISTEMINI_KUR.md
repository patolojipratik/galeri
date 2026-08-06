# Bu sistemi kendi arşivinize uyarlama

Patoloji Pratik Slayt Yayıncısı, başka bir kurum veya kişisel arşiv için uyarlanabilir. Her kurulum kendi GitHub hesabını, repo adlarını, klasörlerini ve güncelleme imzalama anahtarını kullanmalıdır.

## Değiştirilecek temel ayarlar

`config/settings.json` içinde:

```json
{
  "github_username": "kendi-github-kullanici-adiniz",
  "gallery_repo": "galeri",
  "repo_prefix": "gallery-",
  "source_dir": "E:\\Slaytlar",
  "work_root": "E:\\github",
  "update_manifest_url": "https://raw.githubusercontent.com/KULLANICI/GALERI/main/guncelleme/latest.json"
}
```

- `github_username`: yayın yapılacak GitHub kullanıcı/organizasyon adı
- `gallery_repo`: ana galeri reposu
- `repo_prefix`: her sanal slayt için oluşturulan repo öneki
- `source_dir`: KFB/SVS kaynak klasörü
- `work_root`: programın çalışma klasörü
- `update_manifest_url`: kendi güncelleme kanalınızın `latest.json` adresi

## GitHub tokeni

Fine-grained tokeni yalnızca kendi hesap/repolarınızla sınırlandırın. Gereken izinler kullanım biçimine göre şunlardır:

- Contents: Read and write
- Workflows: Read and write
- Actions: Read and write
- Pages: Read and write
- Administration: Read and write

Tokeni `GITHUB_BAGLA.bat` ile Windows kimlik kasasına kaydedin. Tokeni repo içine koymayın.

## Kendi güncelleme anahtarınızı oluşturun

Bağımsız bir sistem kurmadan önce:

```text
YENI_SISTEM_ANAHTARI_OLUSTUR.bat
```

çalıştırın. Bu işlem:

- `config\update_signing_private.key` özel anahtarını,
- `update_trusted_public.key` açık anahtarını

oluşturur.

Özel anahtarı çevrimdışı yedekleyin ve asla GitHub'a yüklemeyin. Açık anahtar uygulamayla dağıtılır. Sistem kullanıcılara dağıtıldıktan sonra anahtarı değiştirmek, eski kullanıcıların yeni paketleri reddetmesine neden olur.

## Güncelleme yayımlama

İmzalanacak güncelleme ZIP'i `update-package.json` içermelidir. Ardından:

```text
GUNCELLEME_YAYINLA.bat
```

çalıştırılır ve ZIP seçilir. Araç:

- paket içi dosya SHA-256 değerlerini doğrular,
- paketi özel anahtarla imzalar,
- `guncelleme/latest.json`, ZIP, SHA-256, imza ve sürüm notlarını hazırlar,
- kendi ana galeri reponuza güvenli bir commit olarak gönderir.

## Korunan kullanıcı verileri

Güncelleme sistemi aşağıdaki yolları içeren paketleri reddeder:

```text
config/
data/
repos/
work/
logs/
.venv/
```

Böylece tanılar, slayt envanteri, GitHub tokeni, yerel repo kalıntıları ve kaynak slaytlar uygulama güncellemesiyle değiştirilemez.

## Lisans ve sorumluluk

Kendi uyarlamanızda kullandığınız üçüncü taraf kütüphanelerin lisanslarını koruyun. Hastaya ait kimlik bilgisi içeren etiketleri veya klinik verileri herkese açık GitHub reposuna yüklemeyin. Yalnızca tamamen anonim eğitim slaytları yayımlayın.
