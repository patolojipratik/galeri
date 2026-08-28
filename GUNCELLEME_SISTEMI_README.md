# Guncelleme sistemi

- Kullanici `BASLAT.bat` calistirir.
- Yerel `guncelleme` klasoru ve GitHub `guncelleme/latest.json` kontrol edilir.
- Yeni paket SHA-256 ve Ed25519 imzasi ile dogrulanir.
- `config`, `data`, `repos`, `work`, `logs` ve `.venv` kullanici alanlari paket tarafindan degistirilemez.
- Kurulan paket `guncelleme/uygulandi` altina tasinir.
- Uygun bakim bilgisayarinda ayni paket GitHub `galeri/guncelleme` kanalina otomatik esitlemeye calisir.
- README.md ve SCREEN.PNG otomatik guncelleme tarafindan degistirilmez.
