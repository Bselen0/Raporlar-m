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


# BLOK YAPISI NEDİR ?
- “Blok yapısı” (block structure), bir depolama cihazındaki verilerin belli boyutlarda parçalara bölünerek saklanması anlamına gelir.

## Basit anlatım:

- Diski küçük kutulara ayırdığını düşün.
- Her kutuya “blok” denir.
- Dosyalar bu bloklara yazılır.

## Neden blok?

- Diskin rastgele veri yazmasını ve okumasını hızlandırır
- Disk yönetimini kolaylaştırır
- Boş alan takibini daha verimli yapar

### Önemli kavramlar
1. Blok Boyutu (Block size)

- Genelde 4 KB, 8 KB, 16 KB gibi olur.
- Küçük blok = daha az boş alan kaybı
- Büyük blok = daha hızlı okuma

2. İnode

Linux dosya sistemlerinde, dosyanın bilgilerini tutan “adres fişi” gibidir:

- dosya sahibi
- izinler
- oluşturulma tarihi
- bloklarda nereye yazıldığı

- ext4, XFS, ZFS gibi sistemlerde inode yapısı çok önemlidir.

3. Fragmentation (Parçalanma)

Bir dosya birden fazla bloğa dağılabilir → okuma yavaşlar.

### Neden blok sistemi var?

- Dosyalar aynı anda milyonlarca parça halinde saklanabilir.
- Arşivleme, kopyalama, veri kurtarma kolaylaşır.
- Disk bozulsa bile bazı bloklar kurtarılabilir.

# HDD vs SSD Çalışma Prensipleri



1. HDD (Hard Disk Drive) Nasıl Çalışır?
## Mekanik sistemdir

- İçinde dönen metal diskler (plaklar) vardır.
- Okuma/yazma kafası bu disk yüzeyine işlem yapar.

## Mantık:

- Tıpkı gramofon gibi döner
- Okuma kafası fiziksel olarak hareket eder

### Özellikleri:

- Daha yavaş
- Darbe alırsa bozulabilir
- Ucuz ve yüksek kapasite sunar

### Teknik olarak:

- Veriler manyetik olarak saklanır.
- Disk döner → kafalar hareket eder → veri bulunur.

## Problem:

- Fat32/NTFS gibi dosya sistemlerinde kötü blok oluşabilir.
- Fragmentation (parçalanma) çok olur.

2. SSD (Solid State Drive) Nasıl Çalışır?
## Elektronik sistemdir

- İçinde hareketli parça yoktur.
- Veriler NAND flash belleklerde saklanır.

## Mantık:

- Tıpkı USB bellek gibi çalışır
- Elektriksel hücreler veri tutar

### Özellikleri:

- Çok hızlı okuma / yazma
- Şoktan etkilenmez
- Sessiz çalışır

### Teknolojiler:

- SATA SSD (orta hız)
- NVMe M.2 SSD (çok yüksek hız)

#### HDD – SSD Teknik Farklar
1. Erişim zamanı

- HDD → milisaniyeler (ms)
- SSD → mikrosaniyeler (µs)

2. Fragmentation etkisi

- HDD → parçalanır ve yavaşlar
- SSD → parçalanma önemli değil

3. Dayanıklılık

- HDD → mekanik parça = bozulma riski
- SSD → elektronik hücre = daha güvenli

4. Blok yapısı ile ilişki

- HDD’de bloklar fiziksel konuma bağlı
- SSD’de bloklar mantıksal adreslemeye bağlı

Bu yüzden SSD için dosya sistemleri (APFS, ext4, BTRFS) daha iyi optimizasyon sunar.

#### SSD’de Özel Terimler
1. Wear Leveling
- Hücrelerin eşit kullanılmasını sağlar (yıpranmayı azaltır).

2. TRIM
- Silinen dosyaların alanının gerçekten boşaltılmasını sağlar (performansı korur).

# Özet

- Blok yapısı = verilerin diskte “kutular” halinde saklanması.
- HDD = manyetik + mekanik + yavaş.
- SSD = elektronik + hızlı + güvenli.
- Modern dosya sistemleri (ext4, APFS, BTRFS) SSD’ye göre optimize edilmiştir.