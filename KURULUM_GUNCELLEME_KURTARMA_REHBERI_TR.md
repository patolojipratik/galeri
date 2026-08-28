# Patoloji Pratik - Kurulum, guncelleme ve kurtarma

## 1. Normal baslatma

Kok klasorde `BASLAT.bat` calistirin. Teknik dosyalari elle acmaniz gerekmez.

## 2. Ilk kullanim / yeni bilgisayar

- SSD veya program klasorunu bilgisayara baglayin.
- `BASLAT.bat` calistirin.
- Surucu harfi degismis olabilir; program kendi konumunu otomatik algilar.
- Kaynak slayt klasoru bulunamazsa secmeniz istenir.
- Python ortami kullanilamiyorsa BASLAT kurulum yolunu yonetir.
- Secilen konumlar `_sistem\konumlar.json` icinde kaydedilir.

## 3. Guncelleme

Elle indirilen imzali guncelleme setinin ZIP, SHA-256 ve SIG dosyalarini:

`<program>\guncelleme`

klasorune koyun ve `BASLAT.bat` calistirin. Yeni surum teklif edilir.

GitHub'dan otomatik guncelleme kontrolu icin token gerekmez. Guncelleme kanalina yeni surum YAYINLAMAK icin bilgisayarda kayitli hedef GitHub tokeni gerekir.

## 4. Guncelleme kanali

Kurulan guncelleme, uygun bakim bilgisayarinda otomatik olarak `patolojipratik/galeri/guncelleme` kanalina esitlemeye calisir.
Elle esitlemek icin `Bakim ve sistem > Guncelleme kanalini esitle` kullanin.

## 5. Web kontrolu

Actions basarili olsa bile tile erisimi ayrica kontrol edilmelidir. `Bakim ve sistem` ekraninda web goruntu kontrolu ve onarimi vardir.

## 6. Yedek

Gunluk kucuk sistem yedegi `slides.csv`, settings ve konum bilgisini korur. Kaynak slaytlar ve token dahil edilmez.

`Kurtarma ZIP'i olustur` ile baska diskte saklanabilecek tek bir kurtarma paketi uretebilirsiniz.

## 7. Kok klasor duzeni

3.8.0 ve sonrasinda kok klasor sade tutulur:

```text
<program>\
  BASLAT.bat
  BURADAN_BASLAYIN.txt
  app\
  config\
  data\
  guncelleme\
  logs\
  repos\
  work\
  github\
  .venv\
  _sistem\
  _belgeler\
  _arsiv\
```

Eski surum notlari, test raporlari ve artik gunluk kullanilmayan kok dosyalari `_arsiv` altina tasinir.
