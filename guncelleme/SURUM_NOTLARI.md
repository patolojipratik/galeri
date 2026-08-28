# Patoloji Pratik Slayt Yayincisi 3.8.1 Final

## Duzeltmeler

- Ana galeri ile `guncelleme/` kanalinin ayni anda GitHub'a commit gondermesi sonucu olusan `fetch first / non-fast-forward` hatasi duzeltildi.
- GitHub uzakta daha yeni commit bulursa uygulama artik **force push yapmadan** `fetch + rebase` ile bir kez guvenli yeniden dener. Cakisma olursa durur ve verileri korur.
- Otomatik guncelleme-kanali esitlemesi ana GUI islem yaparken baslamaz; acilistan sonra sistem bosa cikinca calisir.
- `BASLAT.bat` artik kok klasor sadelestirmesini kullanici onayi olmadan sessizce calistirmaz.
- Program GUI acilisinda hata olursa `logs/startup.log` olusur ve hata penceresi gosterilir; sessizce kapanma azaltilmistir.
- Kok klasor sadeleştirme araci belgeleri `_belgeler`, eski surum/test dosyalarini `_arsiv/gecmis_surumler`, diger eski teknik dosyalari `_arsiv/kok_eski_dosyalar` altina tasir. Kritik klasorler korunur.

## Guvenlik

- `data/slides.csv`, `config`, `repos`, `work`, `.venv`, `guncelleme` ve kaynak slaytlara dokunulmaz.
- GitHub'da `README.md` ve `SCREEN.PNG` korunur.
- `git push --force` kullanilmaz.

## 3.8.0 kullananlar

3.8.0 acilisinda `fetch first` gorduyseniz dosya silmeyin. 3.8.1'i `E:\github\guncelleme` icine koyup BASLAT ile kurun. Ana galeri bir sonraki yayinlamada uzaktaki commit ile yeniden hizalanir.
