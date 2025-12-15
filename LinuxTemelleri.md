# LİNUX TEMELLERİ
Linux, açık kaynak kodlu, çok kullanıcılı ve çok görevli bir işletim sistemidir. Sunucular, gömülü sistemler, yazılım geliştirme ortamları ve siber güvenlik alanlarında yaygın olarak kullanılmaktadır. Linux sistemlerinde kullanıcılar işlemlerini çoğunlukla terminal (komut satırı) üzerinden gerçekleştirir.

## Temel Terminal Komutları
Terminal, Linux işletim sisteminin temel kontrol merkezidir. Kullanıcılar dosya işlemlerini, sistem yönetimini ve program çalıştırmayı terminal komutlarıyla yapar.

1. ls
Bulunulan dizindeki dosya ve klasörleri listeler.
Gizli dosyalar, boyutlar ve izinler gibi bilgiler ek parametrelerle görüntülenebilir.
 ls
 ls -l 
 ls -a
* -l : Detaylı liste (izinler, boyut, tarih)
* -a : Gizli dosyaları da gösterir

2. cd
Dizin değiştirmek için kullanılır.
Kullanıcının dosya sistemi içinde gezinmesini sağlar.
cd Belgeler
cd ..
cd /
* .. : Üst dizine çıkar
* / : Kök dizine gider

3. mkdir
Yeni klasör (dizin) oluşturur.
Proje klasörleri veya sistem yapıları oluşturmak için sıkça 
kullanılır.
mkdir proje
mkdir -p proje/src
* -p : Alt dizinlerle birlikte oluşturur

4. grep
Dosyalar veya komut çıktıları içinde belirli bir kelime ya da ifadeyi arar.
Log dosyalarında hata bulma ve veri filtreleme işlemlerinde etkilidir.
grep "error" log.txt
ls | grep ".txt"

5. chmod
Dosya ve klasörlerin erişim izinlerini düzenler.
Güvenlik ve yetkilendirme açısından kritik bir komuttur.
chmod 755 script.sh
chmod +x program.sh
* 755 : Sahip tüm yetkiler, diğerleri okuma + çalıştırma
* +x : Çalıştırma izni ekler

6. top
Sistemde çalışan işlemleri gerçek zamanlı olarak gösterir.
CPU, RAM kullanımı ve aktif süreçler izlenebilir.

### Paket Yönetimi
Linux’ta yazılımlar paket yöneticileri aracılığıyla yüklenir, güncellenir ve kaldırılır. Bu sistem, yazılım bağımlılıklarını otomatik olarak yönetir.

1. APT (Debian / Ubuntu)
.deb paketlerini kullanır.
Sistem güncellemeleri ve yazılım kurulumları için en yaygın paket yöneticilerindendir.
* sudo apt update
* sudo apt install git
* sudo apt remove nano

2. Pacman (Arch Linux)
Hızlı ve sade yapısıyla bilinir.
Sistemin tamamı tek bir komutla güncellenebilir.
* sudo pacman -Syu
* sudo pacman -S firefox


3. DNF (Fedora / CentOS)
RPM tabanlı sistemlerde kullanılır.
Gelişmiş bağımlılık çözme ve paket yönetimi özelliklerine sahiptir.
* sudo dnf update
* sudo dnf install nginx

** Paket yöneticileri sayesinde yazılım kurulumu manuel dosya indirmeye gerek kalmadan güvenli şekilde yapılır. **

#### Dosya İzinleri
Linux’ta her dosya ve klasör için erişim izinleri tanımlanmıştır. Bu yapı sistem güvenliğinin temelini oluşturur.

* Dosya izinleri üç temel yetkiden oluşur:
1. Okuma (r) : Dosyanın içeriğini görüntüleme
2. Yazma (w) : Dosyayı düzenleme veya silme
3. Çalıştırma (x) : Dosyayı program olarak çalıştırma

* Bu izinler üç kullanıcı grubuna atanır:

1. Sahip (Owner)
2. Grup (Group)
3. Diğer kullanıcılar (Others)

Bu yapı sayesinde kullanıcıların sisteme zarar vermesi veya yetkisiz erişim engellenir.

##### Servis Yönetimi (systemctl)
Linux sistemlerinde servisler genellikle systemd altyapısı ile yönetilir.
Servisler; web sunucuları, veritabanları ve ağ servisleri gibi arka planda çalışan programlardır.

* systemctl komutu ile:
1. Servis başlatılabilir
2. Servis durdurulabilir
3. Servis durumu kontrol edilebilir
4. Sistem açılışında otomatik başlatma ayarlanabilir
* sudo systemctl start nginx
* sudo systemctl stop nginx
* sudo systemctl status nginx
* sudo systemctl enable nginx

Bu yapı, özellikle sunucu sistemlerinde düzenli ve kararlı bir çalışma ortamı sağlar.