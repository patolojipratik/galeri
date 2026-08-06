# Patoloji Pratik Slayt Yayıncısı 3.6.5

Yayın tarihi: 2026-08-06

## Yeni güvenli güncelleme sistemi

- `BASLAT.bat` programı açmadan önce ana galeri reposundaki `guncelleme/latest.json` dosyasını kontrol eder.
- Yeni sürüm bulunduğunda kullanıcı; otomatik indirip kurma, bilgisayardaki ZIP'i seçme, sürüm notlarını açma veya mevcut sürümle devam etme seçeneklerinden birini seçebilir.
- İnternet bağlantısı veya GitHub geçici olarak kullanılamıyorsa program mevcut sürümle açılır.
- Çevrimiçi güncelleme paketleri SHA-256 ve Ed25519 dijital imza ile doğrulanır.
- ZIP içindeki her dosya ayrıca SHA-256 ile denetlenir.
- `config`, `data`, `repos`, `work`, `logs` ve `.venv` yollarına dokunan paketler reddedilir.
- Değişen dosyalar kurulumdan önce yedeklenir; hata durumunda otomatik geri alınır.
- Güncelleme paketi `GUNCELLEME_YAYINLA.bat` ile yerel `patolojipratik` tokeni kullanılarak yayımlanabilir; bu sohbetin bağlı GitHub hesabı kullanılmaz.

## Devir ve uyarlama belgeleri

- `HARICI_SSD_DEVAM_REHBERI.md`: SSD'yi teslim alan kişinin kaldığı yerden devam etmesi için kısa ve güvenli kullanım rehberi.
- `KENDI_SISTEMINI_KUR.md`: aynı yöntemi kendi GitHub hesabı ve slayt arşiviyle kullanmak isteyenler için uyarlama rehberi.
- `BURADAN_BASLAYIN.txt`: SSD kökünde tutulabilecek kısa başlangıç metni.

## Bakım bilgisayarı

Güncelleme yayımlayan bilgisayarda özel imzalama anahtarı bulunur. Bu anahtar halka açık pakete veya GitHub reposuna eklenmez.
