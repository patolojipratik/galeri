# Patoloji Pratik Sanal Mikroskop / Virtual Slide Gallery

[Türkçe](#türkçe) · [English](#english)

---

## Türkçe

Bu depo, **Patoloji Pratik sanal mikroskop galerisinin ana indeksini** ve Windows üzerinde çalışan slayt yayınlama sisteminin güvenli güncelleme kanalını içerir.

Ana galeri: https://patolojipratik.github.io/galeri/

Sistem; KFB, SVS ve OpenSlide ile açılabilen uyumlu tam slayt görüntülerini Deep Zoom Image (DZI) yapısına dönüştürür, her slaytı ayrı `gallery-XXX` deposunda yayımlar ve merkezi galeriyi günceller.

### Nereden başlamalıyım?

- **Hazır harici SSD'yi devraldıysanız:** [Harici SSD ile devam etme ve yeni bilgisayara taşıma](HARICI_SSD_DEVAM_REHBERI.md)
- **Kendi arşiviniz için benzer bir sistem kurmak istiyorsanız:** [Kendi sistemini kurma ve uyarlama](KENDI_SISTEMINI_KUR.md)
- **Patoloji Pratik bakım/yayın bilgisayarı için:** [Yönetici ve bakım rehberi](YONETICI_REHBERI_TR.md)
- **Bir yapay zekâ aracından kurulum yardımı alacaksanız:** [AGENTS.md](AGENTS.md)

### Güncellemeler

Uygulamanın güncel sürümü ve doğrulama bilgisi tek bir kanalda tutulur:

- `guncelleme/latest.json` — makine tarafından okunabilen güncel sürüm bilgisi
- `guncelleme/SURUM_NOTLARI.md` — son sürümde yapılanlar
- `guncelleme/PatolojiPratikSlaytYayincisi_vX.Y.Z.zip` — imzalı güncelleme paketi
- `.sha256.txt` ve dijital imza — paketin doğrulanması için

Kurulu sistemde kullanıcı normal olarak yalnızca `BASLAT.bat` çalıştırır. Yeni sürüm varsa program bunu algılar ve kullanıcıya güncelleme seçeneği sunar.

### Güvenlik ve veri gizliliği

Bu açık depoya GitHub tokeni, özel güncelleme imzalama anahtarı, `data/slides.csv`, yerel `config`, kaynak KFB/SVS dosyaları veya hasta kimliği içeren veriler konulmamalıdır. Yayımlanan eğitim slaytları anonim olmalıdır.

### Yeniden kullanım

Bu yöntemi başka bir eğitim arşivine uyarlamak mümkündür; ancak kendi GitHub hesabınızı, repo adlarınızı, tokeninizi ve **kendi güncelleme imzalama anahtarınızı** kullanın. Ayrıntılar [KENDI_SISTEMINI_KUR.md](KENDI_SISTEMINI_KUR.md) dosyasındadır.

> **Lisans notu:** Bu depoda ayrıca açık bir `LICENSE` dosyası bulunmuyorsa, kodun başkaları tarafından hangi koşullarda yeniden kullanılabileceği açıkça tanımlanmamış demektir. Yeniden kullanımı teşvik etmek için depo sahibi uygun bir açık kaynak lisansı ayrıca seçmelidir.

---

## English

This repository contains the **main index for the Patoloji Pratik virtual microscopy gallery** and the secure update channel for its Windows desktop slide-publishing workflow.

Main gallery: https://patolojipratik.github.io/galeri/

The system converts compatible whole-slide images such as KFB and SVS into a Deep Zoom Image (DZI) structure, publishes each slide in a separate `gallery-XXX` repository, and updates the central gallery.

### Where should I start?

- **Received a preconfigured external SSD:** see [HARICI_SSD_DEVAM_REHBERI.md](HARICI_SSD_DEVAM_REHBERI.md). The guide is in Turkish and covers moving the SSD to another Windows computer, drive-letter changes, Python/Git setup, and recovery.
- **Want to adapt the method to your own archive:** see [KENDI_SISTEMINI_KUR.md](KENDI_SISTEMINI_KUR.md).
- **Using an AI coding/installation assistant:** give it this repository and explicitly ask it to follow [AGENTS.md](AGENTS.md) before changing anything.

### Updates

The canonical update channel is the `guncelleme/` directory:

- `latest.json` — machine-readable current release metadata
- `SURUM_NOTLARI.md` — current release notes
- `PatolojiPratikSlaytYayincisi_vX.Y.Z.zip` — signed update package
- SHA-256 and digital-signature data — package verification

On a configured workstation, the normal entry point is `BASLAT.bat`. It checks the update channel before starting the desktop application.

### Privacy and security

Never publish GitHub tokens, private signing keys, `data/slides.csv`, local configuration, source WSI files, or patient-identifying information in this public repository. Only fully anonymized educational slides should be published.

### Reuse

The workflow can be adapted to another educational archive. Use your own GitHub account, repository names, token and update-signing key. Do not reuse the Patoloji Pratik private signing key.

> **License note:** If this repository does not contain an explicit `LICENSE` file, reuse terms are not yet formally defined. The repository owner should choose an appropriate open-source license before presenting the project as freely reusable software.

---

<!-- PATOLOJI-UPDATE-START -->
## Güncel masaüstü sürümü / Current desktop release

**3.6.7**

- [Güncelleme paketini indir / Download update](guncelleme/PatolojiPratikSlaytYayincisi_v3.6.7.zip)
- [SHA-256](guncelleme/PatolojiPratikSlaytYayincisi_v3.6.7.zip.sha256.txt)
- [Sürüm notları / Release notes](guncelleme/SURUM_NOTLARI.md)
- [Harici SSD ile devam etme](HARICI_SSD_DEVAM_REHBERI.md)
- [Kendi sistemine uyarlama](KENDI_SISTEMINI_KUR.md)
- [Yönetici ve bakım rehberi](YONETICI_REHBERI_TR.md)
- [AI / coding-agent installation guide](AGENTS.md)

Güncelleme ZIP'i kullanıcı verisi, GitHub tokeni, kaynak KFB/SVS dosyaları, `slides.csv`, `config`, `repos`, `work`, `logs` veya `.venv` içermez.
<!-- PATOLOJI-UPDATE-END -->
