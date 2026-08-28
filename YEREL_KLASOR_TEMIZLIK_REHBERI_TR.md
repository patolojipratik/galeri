# E:\github klasorunu guvenli temizleme rehberi

Bu rehber Patoloji Pratik Slayt Yayincisi'nin **calisan kurulumunu bozmadan** eski belge ve test kalintilarini ayirmak icindir.

## 1. Kesinlikle tutulacaklar

Asagidakileri silmeyin veya gelisiguzel tasimayin:

- `app/` — ana program kodu
- `config/` — yerel ayarlar; ozel imzalama anahtari burada olabilir
- `data/` — `slides.csv` dahil en kritik kullanici verisi
- `repos/` — ana galeri yerel reposu ve devam eden/islem icin gereken repo alanlari
- `work/` — aktif veya kurtarilabilir donusum calismalari
- `.venv/` — bu bilgisayardaki Python sanal ortami
- `github/` — kurulumun kullandigi Git/GitHub yardimci dosyalari olabilir
- `guncelleme/` — guncelleyici, yedek ve uygulanmis paket gecmisi
- `logs/` — sorun incelemede yararlidir
- `BASLAT.bat`, `baslat.py`, `baslat_guncelleyici.py`
- `GITHUB_BAGLA.bat`, `github_bagla.py`, `github_bagla_gui.py`
- `GUNCELLEME_YAYINLA.bat`, `guncelleme_yayinla.py`
- `update_crypto.py`, `update_trusted_public.key`, `version.json`
- `anahtar_olustur.py`, `YENI_SISTEM_ANAHTARI_OLUSTUR.bat`
- `requirements.txt`, `.gitignore`
- `WEB_GORUNTU_ONAR.bat`, `WEB_GORUNTU_KONTROL.bat`

`repos/` ve `work/` ozellikle bir slayt islenirken veya yuklenirken temizlenmemelidir.

## 2. Arsive tasinabilecek eski dosyalar

Bunlar calisma zamaninda gerekli degildir; otomatik arac silmek yerine `_arsiv/` altina tasir:

- `public_release/`
- eski `SURUM_NOTLARI_V3_*_FINAL.md` dosyalari
- eski `TEST_RAPORU_V3_*.txt` dosyalari
- `BOYUT_OTOMATIK_KUCULTME_V19.txt`
- `CSV_KILIDI_YAMASI_V18.txt`
- `ILK_ADIMLAR.txt`
- `README_TR.md`
- `README_GITHUB.md`
- `REPO_TEMIZLIK_ONERISI.md`
- `GUNCELLEME_SISTEMI_README.md`

Guncel `SURUM_NOTLARI.md`, `AGENTS.md`, `HARICI_SSD_DEVAM_REHBERI.md`, `KENDI_SISTEMINI_KUR.md`, `KURULUM_GUNCELLEME_KURTARMA_REHBERI_TR.md` ve `YONETICI_REHBERI_TR.md` kokte kalir; guncelleme yayinlayici bunlari GitHub ana galeri reposuna kopyalar.

## 3. Otomatik temizleme

Program kapaliyken once:

```text
E:\github\YEREL_TEMIZLIK_ONIZLE.bat
```

calistirin. Bu **hicbir seyi degistirmez**, sadece adaylari ve boyutlari gosterir.

Liste uygunsa:

```text
E:\github\YEREL_ESKI_DOSYALARI_ARSIVLE.bat
```

calistirin. Dosyalar:

```text
E:\github\_arsiv\YYYYMMDD_HHMMSS\
```

altina tasinir. Python `__pycache__` klasorleri silinir.

## 4. Simdilik dokunulmayan eski araclar

`PAGES_ONAR.bat`, `pages_onar.py`, `GUNCELLE_VE_BASLAT.bat`, `guncelle_oncesi_yedek.py`, `guncelleme_bootstrap.py`, `KURULUM.bat` ve `kurulum.py` bugunku normal kullanimin ana yolu olmayabilir; ancak **kurtarma/yeniden kurulum icin** simdilik tutulur.

## 5. guncelleme klasoru neden buyur?

`guncelleme/uygulandi/` daha once kurulmus paketleri, `guncelleme/yedek/` ise guncelleme oncesi geri-donus kopyalarini tutabilir. Bunlari aktif guncelleme sirasinda silmeyin. Sistem bir sure stabil calistiktan sonra eski paket/yedekler ayrica arsivlenebilir.

GitHub'daki `galeri/guncelleme/` ise farklidir: `GUNCELLEME_YAYINLA.bat` yeni surumu yayinlarken eski ZIP/SHA/imza dosyalarini kaldirir ve yalnizca guncel paketi, `latest.json` ve `SURUM_NOTLARI.md` dosyalarini birakir.


## 3.8.1 notu: GitHub `fetch first`

Ana galeri veya guncelleme kanali ayni anda GitHub'a yazarsa uzakta yeni commit olusabilir. 3.8.1 ve sonrasinda uygulama force push yapmaz; uzaktaki commit'i alir, yerel commit'i onun uzerine guvenli sekilde yeniden uygular ve bir kez tekrar dener. Otomatik birlestirme cakisirsa durur. Bu durumda `data/slides.csv`, kaynak slaytlar ve yayinlanmis repolar silinmez.
