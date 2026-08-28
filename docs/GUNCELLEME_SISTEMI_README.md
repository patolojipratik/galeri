# Patoloji Pratik güvenli güncelleme sistemi

Resmî güncelleme kanalı:

```text
https://github.com/patolojipratik/galeri/tree/main/guncelleme
```

Program güncel sürümü `guncelleme/latest.json` dosyasından öğrenir. Her sürümde ZIP, SHA-256 ve Ed25519 imzası birlikte doğrulanır.

## Normal kullanım

1. `BASLAT.bat` çalıştırılır.
2. Yeni sürüm varsa teklif edilir.
3. Paket doğrulanır ve kurulur.
4. `config`, `data`, `repos`, `work`, `logs` ve `.venv` kullanıcı alanları korunur.
5. Kurulan paket `guncelleme/uygulandi` altına taşınır.
6. Uygun bakım bilgisayarında, uygulama boşta olduğunda aynı sürüm GitHub güncelleme kanalına eşitlenir.

GitHub kanalına yayın sırasında kullanım belgeleri de güncellenir; `README.md` ve `SCREEN.PNG` otomatik değiştirilmez.

## GitHub tokeni ne zaman gerekir?

- Güncellemeyi görmek/indirmek: gerekmez.
- Güncellemeyi kurmak: gerekmez.
- Güncellemeyi GitHub kanalına yayımlamak: gerekir.
- Slayt repo oluşturma/yükleme ve Pages işlemleri: gerekir.

Token Windows kimlik kasasında tutulur; güncelleme ZIP'ine veya kurtarma paketine yazılmaz.
