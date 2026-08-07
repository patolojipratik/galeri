# Patoloji Pratik Slayt Yayıncısı 3.6.7

Yayın tarihi: 2026-08-07

## GitHub güncelleme yayımlama düzeltmesi

- `GUNCELLEME_YAYINLA.bat` artık Windows/Git Credential Manager'da kayıtlı başka GitHub hesaplarını kullanmaz.
- Yayın işlemi yalnızca uygulamanın kendi Windows kimlik kasasında `github_username` için sakladığı tokeni kullanır.
- Örneğin bilgisayarda GitHub Desktop için `metinciris` hesabı açık olsa bile `patolojipratik/galeri` güncellemesi `patolojipratik` tokeniyle gönderilir.
- Bu değişiklik GitHub Desktop oturumunu, global Git ayarlarını veya Windows Credential Manager kayıtlarını silmez/değiştirmez.
- Yanlış hesap nedeniyle görülen `Permission to patolojipratik/galeri.git denied to ...` / HTTP 403 hatası için düzeltmedir.

## Güvenlik

- GitHub tokeni ZIP içine yazılmaz.
- Özel güncelleme imzalama anahtarı pakete eklenmez.
- `config`, `data`, `repos`, `work`, `logs` ve `.venv` kullanıcı verileri güncellenmez.
