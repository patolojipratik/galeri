# Patoloji Pratik Slayt Yayıncısı 3.7.2 Final

Yayın tarihi: 2026-08-28

## Başlık / Tanı web görünümü

- Ana galeri kartında ana kalın satır artık **Başlık** alanıdır.
- **Tanı**, Başlık'tan farklıysa ikinci satırda gösterilir.
- **Organ / sistem** üçüncü satırda gösterilir.
- Ayrıntı penceresi sırası Başlık → Tanı → Organ / sistem → Açıklama olarak düzenlendi.
- Büyük ön izleme başlığında da Başlık esas alınır; Tanı ve Organ alt satırda gösterilir.

## Güncelleme kanalının otomatik eşitlenmesi

- `E:\github\guncelleme` içine konan ve `BASLAT.bat` ile başarıyla kurulan imzalı güncelleme, bu bilgisayarda geçerli hedef GitHub yazma tokeni varsa `patolojipratik/galeri/guncelleme` klasörüne arka planda eşitlenir.
- ZIP, SHA-256, `.sig`, `latest.json`, `SURUM_NOTLARI.md` ve kamuya açık kullanım belgeleri birlikte yayımlanır.
- `README.md` ve `SCREEN.PNG` değiştirilmez.
- GitHub'da daha yeni sürüm varsa eski yerel paket güncelleme kanalını geriye düşürmez.
- Otomatik eşitleme başarısız olursa ana program açılmaya devam eder; `GUNCELLEME_KANALINI_ESITLE.bat` manuel tekrar için eklendi.

## Kullanım belgeleri

- `HARICI_SSD_DEVAM_REHBERI.md` güncellendi.
- `GUNCELLEME_SISTEMI_README.md` güncelleme kanalının tek başvuru belgesi olarak yenilendi.
- `KURULUM_GUNCELLEME_KURTARMA_REHBERI_TR.md` ve `YONETICI_REHBERI_TR.md` yeni otomatik yayın akışını içerir.

## Önceki web görüntü onarımı

3.7.1 ile düzeltilen 076 ve sonrası same-origin Pages/tile yapısı korunmuştur.
