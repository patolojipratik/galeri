# Patoloji Pratik yönetici ve bakım rehberi

Bu belge `patolojipratik` yayın sisteminin kendi bakımımız için kısa kaynak belgesidir. GitHub hesabının şifresi, token değeri veya özel imzalama anahtarı bu belgeye yazılmaz.

## 1. Normal çalışma

Ana giriş noktası:

```text
E:\github\BASLAT.bat
```

Yeni slayt kaynakları:

```text
E:\Pratik_slaytları
```

Ana galeri:

```text
https://patolojipratik.github.io/galeri/
```

Ana repo:

```text
patolojipratik/galeri
```

Slayt repoları:

```text
gallery-001
gallery-002
...
```

## 2. Program güncellemesi yayımlama

**Galeri yayını ile uygulama güncellemesi aynı şey değildir.**

- `BASLAT.bat`: programı açar, güncelleme kontrolü yapar ve normal slayt/galeri iş akışını çalıştırır.
- `GUNCELLEME_YAYINLA.bat`: yeni masaüstü uygulama sürümünü `galeri/guncelleme/` kanalına yayımlar.

Yeni imzalı güncelleme ZIP'i hazır olduğunda bakım bilgisayarında:

```text
E:\github\GUNCELLEME_YAYINLA.bat
```

çalıştırılır ve yeni ZIP seçilir.

Araç:

1. Paketin iç manifestini doğrular.
2. Yerel özel anahtarla paketi imzalar.
3. `guncelleme/latest.json` oluşturur/günceller.
4. ZIP, SHA-256, imza ve sürüm notlarını `guncelleme/` klasörüne koyar.
5. Genel README ve kullanım rehberlerini günceller.
6. Yerel Windows kimlik kasasında kayıtlı `patolojipratik` tokeniyle GitHub'a gönderir.

Bu işlem için bu sohbetin veya başka bir ChatGPT hesabının GitHub bağlantısı gerekli değildir.

## 3. Hangi GitHub API/token ne zaman gerekir?

**Gerekmez:**

- Kullanıcının açık `latest.json` dosyasını kontrol etmesi
- Güncelleme ZIP'ini indirmesi
- SHA-256 / dijital imza doğrulaması
- Yerel Python kurulumu

**Gerekir:**

- Programın yeni `gallery-XXX` deposu oluşturması
- Slaytları GitHub'a göndermesi
- Pages ayarlarını yönetmesi
- Ana galeriyi otomatik göndermesi
- `GUNCELLEME_YAYINLA.bat` ile yeni yazılım sürümünü GitHub'a göndermesi

Token yalnızca Windows kimlik kasasında tutulmalıdır.

## 4. Güncelleme özel anahtarı

Özel imzalama anahtarı bakım bilgisayarında bulunur. GitHub'a veya kullanıcı SSD'sine koymayın.

Kaybedilirse mevcut kurulumların güven zinciri bozulmadan yeni sürüm yayımlamak zorlaşır. Bu nedenle çevrimdışı ikinci bir yedeği olmalıdır.

## 5. Kritik yerel yedekler

Öncelik sırası:

```text
E:\github\data\slides.csv
E:\github\config\settings.json
E:\Pratik_slaytları\
özel güncelleme imzalama anahtarı
```

`.venv`, `work`, `logs` ve temizlenebilir yerel repo kalıntıları yeniden üretilebilir; bunlar ana yedek değildir.

## 6. Ana galeri reposunda tutulması gerekenler

Temel yapı:

```text
README.md
AGENTS.md
HARICI_SSD_DEVAM_REHBERI.md
KENDI_SISTEMINI_KUR.md
YONETICI_REHBERI_TR.md
index.html
slides.json
.nojekyll
thumbs/
guncelleme/
```

`guncelleme/` içinde yalnızca **güncel sürüm** paketinin tutulması yeterlidir; yayın aracı eski güncelleme ZIP'lerini temizleyebilir.

## 7. Ana galeride hata olduğunda

Önce hatanın türünü ayırın:

- Git push başarılı ama Pages bekliyor → Pages/Actions durumu
- `Service Unavailable` → çoğunlukla GitHub altyapısı; hemen tekrar tekrar tetiklemeyin
- token/403 → yetki veya token sorunu
- web sayfası açılıyor ama içerik eski → `slides.json`/Pages doğrulaması

Başarılı yayımlanmış slayt repolarını yalnızca Pages geçici hata verdi diye silmeyin.

## 8. Kötü yükleme silme

Sadece gerçekten bozuk veya yanlış slayt için kullanın. Geçici Actions/Pages problemi kötü yükleme değildir.

## 9. Yeni bilgisayara taşıma

Ayrıntılı basit rehber:

[HARICI_SSD_DEVAM_REHBERI.md](HARICI_SSD_DEVAM_REHBERI.md)

Özet: sürücü harfini mümkünse `E:` yapın, Python 3.10+ ve Git kurun, eski `.venv` klasörünü yeniden oluşturun, token gerekiyorsa `GITHUB_BAGLA.bat` ile kaydedin.
