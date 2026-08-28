# Patoloji Pratik güvenli güncelleme sistemi

Bu dosya hem normal kullanıcı hem de sistemi yöneten kişi için kısa başvuru kaynağıdır.

## Güncelleme kanalı

Resmî güncelleme kanalı ana galeri reposundaki şu klasördür:

```text
https://github.com/patolojipratik/galeri/tree/main/guncelleme
```

Program yeni sürümü şu dosyadan öğrenir:

```text
guncelleme/latest.json
```

Güncel bir sürümde kanalda birlikte bulunması gereken dosyalar:

```text
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sha256.txt
PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sig
latest.json
SURUM_NOTLARI.md
```

ZIP tek başına güvenilir güncelleme sayılmaz. SHA-256 ve Ed25519 imzası doğrulanır.

## Kullanıcı güncellemeyi nasıl kurar?

1. Aktif slayt işi varsa bitmesini bekleyin.
2. Ekranda **GÜVENLE KAPATABİLİRSİNİZ** görünce programı kapatın.
3. Size verilen ZIP, `.sha256.txt` ve `.sig` dosyalarını açmadan:

```text
E:\github\guncelleme
```

klasörüne koyun.
4. `E:\github\BASLAT.bat` çalıştırın.
5. Yeni sürüm sorulduğunda **Güncellemeyi indir ve kur** seçeneğini kabul edin.
6. Güncelleme doğrulanır, yedek alınır ve program yeni sürümle açılır.

## Yerel kurulumdan GitHub güncelleme kanalına otomatik eşitleme

3.7.2 ve sonrasında, bilgisayarda hedef GitHub hesabı için geçerli yayın tokeni varsa, yerel olarak başarıyla kurulmuş güncelleme ana galeri reposundaki `guncelleme/` klasörüne arka planda eşitlenir.

Bu işlem yalnızca güncelleme dosyalarını ve kullanım belgelerini gönderir. `README.md`, `SCREEN.PNG`, `slides.csv`, kaynak KFB/SVS dosyaları ve slayt repoları değiştirilmez.

Otomatik eşitleme başarısız olursa program yine açılır. Manuel tekrar için:

```text
E:\github\GUNCELLEME_KANALINI_ESITLE.bat
```

kullanılabilir.

## Hangi durumda GitHub API/token gerekir?

- Güncellemeyi **görmek ve indirmek**: gerekmez; repo publictir.
- Güncellemeyi **kurmak**: gerekmez.
- Güncellemeyi `patolojipratik/galeri/guncelleme` klasörüne **yayımlamak**: GitHub yazma tokeni gerekir.
- Slayt repo oluşturma/yükleme ve Pages ayarları: token gerekir.

Token dosyaya, rehbere veya GitHub reposuna yazılmaz; Windows kimlik kasasında tutulur.

## Güncelleme kanalını geriye düşürme koruması

Yayın aracı GitHub'daki `latest.json` sürümünü kontrol eder. GitHub'da daha yeni bir sürüm varsa eski yerel paket kanalı geriye düşürmez.
