# Patoloji Pratik Slayt Yayıncısı — Yönetici Rehberi

Bu belge mevcut `patolojipratik` kurulumunun bakım ve sürüm yönetimi içindir.

## Normal iş akışı

- Kaynak slaytlar: `E:\Pratik_slaytları`
- Program: `E:\github\BASLAT.bat`
- Ana galeri repo: `patolojipratik/galeri`
- Güncelleme kanalı: `patolojipratik/galeri/guncelleme`

Aktif işlem bitmeden programı/SSD'yi kapatmayın.

## Güncelleme yayınlama — 3.7.2 ve sonrası

Yeni imzalı paket (ZIP + SHA-256 + `.sig`) `E:\github\guncelleme` klasörüne konup `BASLAT.bat` ile başarıyla kurulunca, bilgisayarda geçerli `patolojipratik` yayın tokeni varsa yeni sürüm GitHub `guncelleme/` kanalına otomatik eşitlenir.

Otomatik eşitlemenin sonucu:

```text
E:\github\logs\update_channel_sync.log
```

ile izlenebilir.

Manuel tekrar:

```text
E:\github\GUNCELLEME_KANALINI_ESITLE.bat
```

Bu işlem yalnızca güncelleme dosyalarını ve kamuya açık rehberleri yayımlar. `README.md` ve `SCREEN.PNG` dokunulmaz.

Yayın aracı GitHub'da daha yeni sürüm varsa eski paketi yayımlayarak kanalı geriye düşürmez.

## Başlık / Tanı web gösterimi

3.7.2 ile ana galeride standart:

1. Başlık — kartın ana kalın satırı
2. Tanı — başlıktan farklıysa ikinci satır
3. Organ / sistem — üçüncü satır

Ayrıntı panelinde Başlık → Tanı → Organ / sistem → Açıklama sırası kullanılır.

Bu düzeltmenin ana siteye geçmesi için 3.7.2 kurulduktan sonra bir kez **Ana galeriyi yayımla** çalıştırın.

## Web viewer kurtarma

076 ve sonrası için `WEB_GORUNTU_ONAR.bat`, repo içindeki tile verilerini yeniden bilgisayardan yüklemeden viewer/workflow dosyalarını onarır. Actions bittikten sonra `WEB_GORUNTU_KONTROL.bat` kullanın.

## Kritik veriler

Silinmemesi gerekenler:

```text
config/
data/
repos/
work/
.venv/
guncelleme/
app/
```

Eski sürüm notları/test raporları `_arsiv` altına taşınabilir. `__pycache__` yeniden üretilebilir.

## Gizli bilgiler

- GitHub tokeni repoya yazılmaz.
- `config/update_signing_private.key` yalnızca bakım/yayın bilgisayarında tutulur ve halka açık pakete eklenmez.
- `update_trusted_public.key` halka açık doğrulama anahtarıdır ve programda bulunabilir.
