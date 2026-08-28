# Harici SSD ile devam etme rehberi

## Gunluk kullanim

Normal kullanimda kok klasorde yalnizca `BASLAT.bat` dosyasina cift tiklayin.
Program teknik dosyalari `_sistem`, belgeleri `_belgeler`, eski dosyalari `_arsiv` altinda tutar.

## SSD baska bilgisayarda farkli harf alirsa

Artik `E:` olmak zorunda degildir. `BASLAT.bat` kendi bulundugu klasoru program konumu olarak algilar.
Ornegin SSD `F:` olursa program `F:\github` konumunu otomatik kullanir.

Kaynak KFB/SVS klasoru eski konumda bulunamazsa program once ayni SSD uzerinde `Pratik_slaytlari` klasorunu arar. Bulamazsa klasoru secmenizi ister ve seciminizi kaydeder.

## Python yoksa

`BASLAT.bat` once mevcut Python ortamini dener. Kullanilabilir ortam yoksa:

1. Bilgisayarda Python 3.10+ arar.
2. Bulursa `.venv` ortamini yeniden olusturur ve gereksinimleri kurar.
3. Python yoksa Windows `winget` mevcutsa Python 3.12 kurulumunu teklif eder.
4. Otomatik kurulum kullanilamazsa resmi Python indirme sayfasini acar.

## PC guvenlik yedegi

Program `slides.csv`, ayarlar ve konum bilgileri gibi kucuk kritik dosyalari bilgisayarda ayrica saklayabilir. Kaynak KFB/SVS dosyalari bu yedege alinmaz.

Varsayilan yer genellikle:

`Belgeler\PatolojiPratik_Yedek`

Konumu `Bakim ve sistem > Konumlar ve ilk kurulum` ekranindan degistirebilirsiniz.

## Bakim ve sistem

Ana penceredeki `Bakim ve sistem` dugmesinde:

- Sistem saglik kontrolu
- Konumlar ve ilk kurulum
- Guvenlik yedegi
- Kurtarma ZIP'i
- Web goruntulerini kontrol/onarma
- Guncelleme kanalini esitleme
- Yerel temizlik onizleme

bulunur.

## SSD veya bilgisayar arizasi

`Bakim ve sistem > Kurtarma ZIP'i olustur` ile uretilen ZIP'i ayrica saklayin. Bu ZIP GitHub tokenini ve kaynak slaytlari icermez. Kaynak slaytlarin da ayri bir yedegi olmalidir.

## GitHub tokeni

Tokeni sohbet, ekran goruntusu veya duz metin dosyasinda paylasmayin. Normal kullanimda token Windows kimlik kasasinda tutulur.
