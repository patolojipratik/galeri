# Patoloji Pratik — Kurulum, Güncelleme, Yayınlama ve Kurtarma Rehberi

## 1. Günlük başlatma

```text
E:\github\BASLAT.bat
```

Program yeni sürümü otomatik kontrol eder. Güncelleme yoksa doğrudan açılır.

## 2. Güncelleme dosyası size ZIP olarak geldiyse

Üç dosyayı birlikte indirin:

```text
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sha256.txt
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sig
```

Hepsini açmadan `E:\github\guncelleme` içine koyun. `BASLAT.bat` çalıştırın ve yeni sürümü kabul edin.

## 3. GitHub güncelleme kanalı

Kanal:

```text
https://github.com/patolojipratik/galeri/tree/main/guncelleme
```

3.7.2 ve sonrasında yerel güncelleme başarıyla kurulduktan sonra geçerli yayın tokeni bulunan bakım bilgisayarı paketi otomatik olarak bu kanala eşitler. Kanalda ZIP, SHA-256, imza, `latest.json` ve `SURUM_NOTLARI.md` birlikte tutulur.

Manuel eşitleme gerekiyorsa:

```text
E:\github\GUNCELLEME_KANALINI_ESITLE.bat
```

Güncellemeyi yalnızca indiren kullanıcının GitHub tokenine ihtiyacı yoktur. GitHub'a güncelleme/slayt **yazan** bilgisayarda token gerekir.

## 4. Ana galeri

Ana galeri:

```text
https://patolojipratik.github.io/galeri/
```

3.7.2 ile kartlarda **Başlık → Tanı → Organ / sistem** sırası kullanılır. Güncellemeden sonra bu görünümü yayımlamak için bir kez **Ana galeriyi yayımla** düğmesini kullanın.

`README.md` ve `SCREEN.PNG` otomatik galeri/güncelleme yayınlarında korunur.

## 5. Web slaytları karanlık/açılmıyorsa

```text
E:\github\WEB_GORUNTU_ONAR.bat
```

sonra GitHub Actions'ın tamamlanmasını bekleyin ve:

```text
E:\github\WEB_GORUNTU_KONTROL.bat
```

çalıştırın. Geçici GitHub hatasında slayt repolarını silmeyin.

## 6. Başka bilgisayara geçiş

SSD `E:` değilse mümkünse Disk Yönetimi'nden `E:` yapın. Aksi halde `config/settings.json` yollarını yeni sürücü harfine göre değiştirin.

Python 3.10+ 64-bit ve Git for Windows kurulu olmalıdır. `.venv` taşınan bilgisayarda sorun çıkarırsa yeniden oluşturulabilir; `data`, `config` ve kaynak slaytları silmeyin.

## 7. SSD arızası / kurtarma

Ayrı yedek tutulması gerekenler:

```text
E:\github\data\slides.csv
E:\github\config\settings.json
kaynak KFB/SVS dosyaları
```

GitHub'da yayınlanmış `gallery-XXX` repoları ikinci bir kurtarma kaynağıdır; aceleyle silinmemelidir.

## 8. Ayrıntılı belgeler

- `HARICI_SSD_DEVAM_REHBERI.md`
- `GUNCELLEME_SISTEMI_README.md`
- `YONETICI_REHBERI_TR.md`
- `KENDI_SISTEMINI_KUR.md`
- `AGENTS.md`
