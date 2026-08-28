# Patoloji Pratik Slayt Yayıncısı 3.8.3 Final

## Ana düzeltme: yeni arayüzün gerçekten yüklenmesi

3.8.0–3.8.2 klasör sadeleştirmesinden sonra `_sistem/start_app.py`, `app.log_manager` modülünü ana GUI kimliği (`baslat.py`) ayarlanmadan önce içe aktarabiliyordu. Bu nedenle `app/__init__.py` GUI iyileştirmelerini kurmadan önbelleğe giriyor; program çalışsa da pencere başlığında **3.6.5 Final** kalabiliyor ve **Rehberler / Bakım ve sistem** düğmeleri görünmüyordu.

3.8.3'te başlatma sırası düzeltildi ve GUI bootstrap açıkça, idempotent biçimde çağrılıyor.

Beklenen sonuç:

- başlıkta **3.8.3 Final**,
- modern arayüz,
- **Rehberler** düğmesi,
- **Bakım ve sistem** düğmesi,
- bakım ekranında yedek/log durum alanı ve bakım araçları.

## Dokümantasyon düzeni

GitHub deposunda belgeler kolay dolaşılan yapıya alınır:

- `README.md`: Türkçe + English ana tanıtım ve yol gösterme,
- `REHBERLER.md`: tek dokümantasyon menüsü,
- `HARICI_SSD_DEVAM_REHBERI.md`: SSD, evden çalışma, Bakım ve sistem, yedek/kurtarma,
- `AGENTS.md`: AI/coding agent güvenlik talimatları,
- `docs/`: ayrıntılı yönetim/kurulum belgeleri,
- `guncelleme/`: yalnızca güncel paket, SHA-256, imza, latest.json ve sürüm notları.

3.8.3 yayınında yanlışlıkla kısalmış README **bir kez** istenen kapsamlı sürümle geri yüklenir. Sonraki normal güncellemeler README'yi otomatik değiştirmez.

Eski/çift kök belgeler ile çok eski `v3.3.1` dağıtım dosyası ve eski `surum.json` GitHub kökünden kaldırılır. Ana galeri verileri (`index.html`, `slides.json`, `slayt_bilgileri.csv`, `thumbs/`) ve `SCREEN.PNG` korunur.

## Güvenlik

- Force push kullanılmaz.
- Kullanıcı `data`, `config`, kaynak slaytlar ve token güncelleme paketine alınmaz.
- README temizliği yalnızca 3.8.3'ün tek seferlik repo düzenlemesidir.
