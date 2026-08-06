# Harici SSD ile devam etme rehberi

Bu rehber, hazırlanmış Patoloji Pratik harici SSD'sini teslim alan kişinin kaldığı yerden güvenli biçimde devam edebilmesi içindir.

## Başlatma

Varsayılan klasörler:

```text
E:\Pratik_slaytları   Kaynak KFB/SVS slaytları
E:\github             Program ve çalışma dosyaları
```

SSD `E:` dışında bir harf aldıysa Windows Disk Yönetimi'nden sürücü harfini `E:` yapın. Alternatif olarak `E:\github\config\settings.json` içindeki `source_dir` ve `work_root` yollarını yeni sürücü harfine göre değiştirin.

Programı yalnızca şu dosyayla açın:

```text
E:\github\BASLAT.bat
```

`BASLAT.bat` önce güncelleme kontrolü yapar, varsa kullanıcıya seçenek gösterir ve ardından ana programı açar. İnternet yoksa mevcut sürümle devam eder.

## Güncelleme seçenekleri

Yeni sürüm bulunduğunda:

- **Güncellemeyi indir ve kur:** ZIP'i indirir, SHA-256 ve dijital imzayı doğrular, yedek alır ve kurar.
- **Bilgisayarımdaki ZIP dosyasını seç:** daha önce indirilen güncelleme paketini seçtirir.
- **Sürüm notlarını aç:** yapılan değişiklikleri gösterir.
- **Şimdilik mevcut sürümle devam et:** güncellemeden programı açar.

Güncelleme başarısız olursa eski dosyalar geri yüklenir. Kullanıcı verileri güncelleme paketleri tarafından değiştirilemez.

## Normal kullanım

- **Sıradaki 1 Slaytı İşle:** yalnızca sıradaki slaytı işler.
- **Tümünü İşle:** bekleyen tüm slaytları sırayla işler.
- **Mevcut Slaytı Bitir ve Dur:** aktif slaytı tamamlar ve yeni slayta başlamaz.
- **Slayt bilgilerini düzenle:** başlık, organ, tanı, açıklama ve etiketleri değiştirir.
- **Ana galeriyi yayımla:** ana galeri dosyalarını GitHub'a gönderir.
- **Yayınları şimdi kontrol et:** GitHub'a yüklenmiş fakat web yayını henüz doğrulanmamış slaytları denetler.

Programda **GÜVENLE KAPATABİLİRSİNİZ** yazmadan bilgisayarı kapatmayın ve SSD'yi çıkarmayın.

## Yeni slayt ekleme

Anonim KFB/SVS dosyalarını şu klasöre kopyalayın:

```text
E:\Pratik_slaytları
```

Program sonraki açılışta yeni dosyaları bulur ve sıra sonuna ekler.

## Kötü yükleme

Geçici GitHub Actions veya Pages hatası kötü yükleme değildir. Yalnızca görüntüsü gerçekten hatalı slaytta **Kötü Yüklemeyi Tamamen Kaldır** işlemini kullanın. Kaynak dosya `E:\Pratik_slaytları\yüklenmeyen` klasörüne taşınır.

## GitHub hesabı

SSD'yi kullanan kişiye GitHub hesabının e-posta adresi veya şifresi verilmez. Mevcut token geçerliyse program yayın yapmayı sürdürür. Token süresi dolarsa hesap sahibi yeni token oluşturup `GITHUB_BAGLA.bat` ile kaydetmelidir.

Tokeni sohbetlere, ekran görüntülerine veya düz metin dosyalarına yazmayın.

## Yedek

Özellikle şu dosyanın başka bir diskte yedeğini tutun:

```text
E:\github\data\slides.csv
```

Kaynak slaytların tek kopyası yalnızca bu SSD üzerinde olmamalıdır.
