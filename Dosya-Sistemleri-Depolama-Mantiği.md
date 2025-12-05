# 🖥️ Dosya Sistemleri: NTFS – ext4 – APFS

Bu rapor, üç popüler dosya sistemi olan **NTFS, ext4 ve APFS** yapılarını; kullanım alanlarını, avantajlarını ve temel farklarını açıklamaktadır.

---

## 🔷 1. NTFS (New Technology File System)

**Geliştirici:** Microsoft  
**Kullanım Alanı:** Windows işletim sistemi

### ✔ Avantajları
- Büyük dosya boyutlarını destekler
- Dosya ve klasör izinleri güçlüdür
- Disk hatası kontrolü (journaling) yapar
- Gelişmiş özelliklere sahiptir:
  - Dosya şifreleme
  - Gölge kopyalar (shadow copies)
  - Dosya sıkıştırma

### ✔ Nerelerde Kullanılır?
- Windows işletim sistemi
- Harici diskler ve HDD / SSD'ler (Windows kullanıcıları için)

---

## 🔷 2. ext4 (Fourth Extended File System)

**Geliştirici:** Linux topluluğu  
**Kullanım Alanı:** Linux dağıtımları

### ✔ Avantajları
- Stabil, hızlı ve güvenilirdir
- Journaling desteği sayesinde veri kaybı riskini azaltır
- Büyük diskleri ve dosya boyutlarını destekler(1 EB ve üzeri teorik sınır)
- SSD performansına uygundur

### ✔ Nerelerde Kullanılır?
- Sunucu işletim sistemleri
- Ubuntu, Kali, Fedora, Debian vb.


Not: ext4, özellikle sunucu ve web hosting alanında en çok tercih edilen sistemdir.

---

## 🔷 3. APFS (Apple File System)

**Geliştirici:** Apple  
**Kullanım Alanı:** macOS, iOS, iPadOS, watchOS, tvOS

### ✔ Avantajları
- SSD ve flash bellekler için optimize edilmiştir
- Hızlı klonlama (copy-on-write)
- Snapshot (anlık görüntü alma) desteği
- Güçlü dosya şifreleme seçenekleri

### ✔ Nerelerde Kullanılır?
- MacBook
- iPhone
- iPad
- Apple Watch

---

## Karşılaştırma (Maddeler Halinde)

### Performans farkı
- **NTFS:** HDD ve SSD’de genel kullanım için iyidir.
- **ext4:** Özellikle Linux sistemlerde yüksek performans sağlar.
- **APFS:** SSD’de en yüksek performansı hedefler.

### Güvenlik
- **NTFS:** Gelişmiş izin sistemi ve şifreleme mekanizması sunar.
- **ext4:** İzin sistemi vardır ancak NTFS kadar gelişmiş değildir.
- **APFS:** Şifreleme konusunda en güçlü olan dosya sistemidir.

### Veri bütünlüğü
- Üç sistemin de journaling özelliği vardır, bu nedenle veri kaybı riski azaltılır.
- **APFS**, snapshot desteği sayesinde kayıp durumunda geriye dönüş imkânı sağlar.

### Uyum
- **NTFS:** Windows ile en uyumlu dosya sistemidir.
- **ext4:** Linux sistemler ile en uyumludur.
- **APFS:** Apple cihazlarında tam performans gösterir.

### Evrenellik (birden çok sistemde kullanım)
- **NTFS:** Linux ve Mac tarafından okunabilir ama yazma desteği sorunlu olabilir.
- **ext4:** Windows tarafından doğal olarak desteklenmez.
- **APFS:** Apple dışındaki cihazlarda pek desteklenmez.



---

##  5. Sonuç (Basit Özet)

- **Windows kullanıyorsan:** NTFS en iyi tercih  
- **Linux kullanıyorsan:** ext4 kesinlikle önerilir  
- **Apple cihazları için:** APFS hız + güvenlik sağlar  

Her dosya sistemi kendi ekosistemine uygun şekilde maksimum performans göstermektedir.

---

##  6. Ek Bilgi

### FAT32 ve exFAT ne işe yarar?
- **FAT32:** Her yerde çalışır ama 4 GB üzeri dosya taşıyamaz
- **exFAT:** Büyük dosyaları destekler, farklı işletim sistemleri arasında veri taşımak için idealdir

---


