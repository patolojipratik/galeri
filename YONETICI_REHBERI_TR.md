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


## 3.8.1 notu: GitHub `fetch first`

Ana galeri veya guncelleme kanali ayni anda GitHub'a yazarsa uzakta yeni commit olusabilir. 3.8.1 ve sonrasinda uygulama force push yapmaz; uzaktaki commit'i alir, yerel commit'i onun uzerine guvenli sekilde yeniden uygular ve bir kez tekrar dener. Otomatik birlestirme cakisirsa durur. Bu durumda `data/slides.csv`, kaynak slaytlar ve yayinlanmis repolar silinmez.
