# Patoloji Pratik Slaytları / Patoloji Pratik Virtual Slides

Sanal mikroskop ana galerisi ve Patoloji Pratik Slayt Yayıncısı için ana kaynak deposu.

Main repository for the Patoloji Pratik virtual microscopy gallery and the Patoloji Pratik Slide Publisher.

![Patoloji Pratik Slayt Yayıncısı](SCREEN.PNG)

## Türkçe

### Ne işe yarar?

Patoloji Pratik Slayt Yayıncısı; KFB ve SVS tam slayt görüntülerini sanal mikroskop biçimine dönüştürür, GitHub üzerinde yayımlar ve ana galeriyi güncel tutar.

Ana galeri:

- https://patolojipratik.github.io/galeri/

### Güncel masaüstü uygulaması

Güncel sürüm bilgisi ve indirilecek paketler:

- [Güncelleme klasörü](guncelleme/)
- [Güncel sürüm bilgisi](guncelleme/latest.json)
- [Son sürüm notları](guncelleme/SURUM_NOTLARI.md)

> Güncel ZIP dosyasının adı `guncelleme/latest.json` içindeki `package` alanında yazılıdır.

Yayımlanan uygulama paketleri kullanıcı verisi içermez. GitHub tokeni, `config`, `data/slides.csv`, `repos`, `work`, `logs` ve kaynak KFB/SVS dosyaları dağıtım paketine alınmaz.

### Hazır harici SSD ile devam edecek kişi

Elinizde daha önce hazırlanmış Patoloji Pratik harici SSD'si varsa:

- [Harici SSD ile devam etme ve yeni bilgisayara taşıma rehberi](HARICI_SSD_DEVAM_REHBERI.md)

Bu rehber; SSD `E:` değilse ne yapılacağını, Python/Git kurulumunu, başka bilgisayarda nasıl devam edileceğini ve SSD arızası sonrası kurtarmayı basit sırayla açıklar.

### Sistemi sıfırdan kendine kurmak isteyenler

Kendi GitHub hesabınız ve kendi slayt arşivinizle benzer bir sistem kurmak için:

- [Kendi sistemini kurma rehberi](KENDI_SISTEMINI_KUR.md)

Bu sistem kendi GitHub kullanıcı adınıza, repo adlarınıza, klasörlerinize ve güncelleme kanalınıza uyarlanabilir.

### Patoloji Pratik yöneticisi için

Patoloji Pratik'in mevcut kurulumunun bakım, güncelleme ve devir notları:

- [Yönetici rehberi — Türkçe](YONETICI_REHBERI_TR.md)

Bu belge genel kullanıcı rehberi değildir.

### Yapay zekâ ile kurulum

Bu repoyu bir yapay zekâ aracına verip sistemi kurdurmak veya taşımak istiyorsanız yapay zekâya önce şu dosyayı okutun:

- [AGENTS.md — AI kurulum ve güvenlik talimatları](AGENTS.md)

Yapay zekâ; kullanıcı verilerini, tokeni, `slides.csv` dosyasını ve mevcut yayınlanmış `gallery-XXX` repolarını silmeden işlem yapmalıdır.

### Slayt bilgilerini düzenleme

Başlık, organ, tanı, açıklama ve etiketler masaüstü uygulamasındaki **Slayt bilgilerini düzenle** penceresinden yönetilir.

Ana sayfa küçük ön izlemeleri kullanır; büyük ön izlemeler yalnızca kullanıcı istediğinde yüklenir.

---

## English

### What does it do?

Patoloji Pratik Slide Publisher converts KFB and SVS whole-slide images into a virtual microscopy format, publishes them through GitHub, and maintains the main gallery.

Main gallery:

- https://patolojipratik.github.io/galeri/

### Latest desktop application

The current version and downloadable update files are available here:

- [Update directory](guncelleme/)
- [Current version manifest](guncelleme/latest.json)
- [Latest release notes](guncelleme/SURUM_NOTLARI.md)

> The current ZIP filename is stored in the `package` field of `guncelleme/latest.json`.

Public application packages do not contain user data, GitHub tokens, local configuration, `slides.csv`, working repositories, logs, or source KFB/SVS slides.

### Continue from an existing external SSD

For a computer that already has a prepared Patoloji Pratik external SSD:

- [External SSD continuation guide — Turkish](HARICI_SSD_DEVAM_REHBERI.md)

It explains drive-letter changes, Python/Git setup, moving to another Windows computer, and recovery after SSD/computer problems.

### Build a similar system for your own archive

To adapt the method to your own GitHub account and slide archive:

- [Build your own system — Turkish](KENDI_SISTEMINI_KUR.md)

### Installation with an AI assistant

If an AI coding assistant is going to install, migrate, repair, or adapt this repository, it should read this file first:

- [AGENTS.md](AGENTS.md)

The AI must preserve user data, credentials, `slides.csv`, source slides, and already-published repositories unless the operator explicitly requests otherwise.

---

## Güncelleme yapısı / Update structure

```text
galeri/
├── README.md
├── SCREEN.PNG
├── AGENTS.md
├── HARICI_SSD_DEVAM_REHBERI.md
├── KENDI_SISTEMINI_KUR.md
├── YONETICI_REHBERI_TR.md
├── index.html
├── slides.json
├── thumbs/
└── guncelleme/
    ├── latest.json
    ├── SURUM_NOTLARI.md
    ├── PatolojiPratikSlaytYayincisi_vX.Y.Z.zip
    ├── PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sha256.txt
    └── PatolojiPratikSlaytYayincisi_vX.Y.Z.zip.sig
```

`README.md` ve `SCREEN.PNG` kalıcı repo belgeleridir; normal galeri veya uygulama güncellemesi bunları değiştirmemelidir.
