# Patoloji Pratik yonetici rehberi

## Temel ilke

Gunluk kullanimda yalnizca `BASLAT.bat` kullanilir. Uygulama cekirdegi, config/data ve kaynak slaytlar elle temizlenmez.

## Kok duzen

- `_sistem`: calistiricilar, guncelleyici, teknik araclar
- `_belgeler`: kullanim ve kurulum dokumani
- `_arsiv`: eski raporlar ve kok klasorden kaldirilan eski dosyalar
- `guncelleme`: bekleyen/uygulanmis imzali paketler
- `data`: slayt envanteri
- `config`: ayarlar ve yerel yonetici anahtarlari
- `repos`, `work`: yayin isleminin calisma alanlari

## Konum tasinabilirligi

Program `work_root` degerini kendi calistigi klasore gore gunceller. Kaynak klasor bulunamazsa ayni disk ve diger disk koklerinde arar; gerekirse kullaniciya sorar.

## Guncelleme yayini

Guncelleme kanali `galeri/guncelleme` klasorudur. Kurulan surum uygun token varsa otomatik esitlemeye calisir. Manuel yol `Bakim ve sistem > Guncelleme kanalini esitle` secenegidir.

## Guvenlik

Token repoya yazilmaz. Kurtarma ZIP'i token veya kaynak slayt icermez. Ozel guncelleme imzalama anahtari `config` altinda kalir ve public GitHub'a gonderilmez.
