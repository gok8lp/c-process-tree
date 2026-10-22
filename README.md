# C Process Tree

C ve POSIX süreçleri üzerine küçük bir öğrenme projesi.
A small learning exercise about process trees using `fork()` and file-based communication.

`process_tree.c`, iki alt süreç oluşturarak bir ağaç kurar. Yaprak süreçler rastgele bir sayıyı
PID adını taşıyan `.txt` dosyasına yazar; ebeveyn süreçler çocukların dosyalarını okuyup toplamayı dener.

## Derleme

Linux veya POSIX `fork()` desteği olan bir ortam ve C derleyicisi gerekir.

```bash
gcc -std=c11 -Wall -Wextra process_tree.c -o process_tree
mkdir -p output
cd output
../process_tree
```

Çalışma dizininde PID isimli dosyalar oluşur; örnek bu yüzden ayrı `output` dizininde çalıştırılır.

## Öğrenilecek konular ve mevcut sınırlar

`fork`, PID, ebeveyn/çocuk süreç, `wait` ve dosya üzerinden veri paylaşımı.
Bu düzenlemede çocuk dosyasının doğru PID ile okunması ve iki çocuğun `waitpid` ile beklenmesi düzeltildi.
Dosya açma/fork hataları hâlâ tam işlenmez; örnek sabit derinlikli bir ders denemesidir.
Üretim amaçlı süreç yönetimi örneği olarak değerlendirilmemelidir.
