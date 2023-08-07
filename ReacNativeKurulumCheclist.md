Android Emulator Kurulum Checklist
Sorun yasamamak icin llutfen asagidaki checklist'i uygula

1. Java Sdk indir(Versiyon 12.0.2) (https://www.oracle.com/java/technologies/javase-downloads.html)

2. node js indir (https://nodejs.org/en/). Soldaki seçeneği seçin.(Recommended one)

3. Python indir(Versiyon 2...) (https://www.python.org/downloads/release/python-2718/)

4. Android-Studio indir ve kur.(Version 3...)

5. Terminali aç ve administrator(yönetici) olarak çalıştır.

6. Terminalde "npm install -g react-native-cli" komutunu çalıştır.

7. Terminalden projeni koymak istediğin klasöre git ve bu klasörde "react-native init cars" komutunu çalıştır.

8. Android-Studio kurulumunu yaparken "Start Android-Studio" seçeneğini kaldır.

9. Windows arama çubuğunu aç ve buraya Android-Studio yazıp tıkla.

10. Android-Studio kurulumunda ilerlerken SDK Components Setup ekranında. "Android SDK Location"a git ve burada klasör ikonuna tıkla, burada D: sürücüsünü seç ve sağ tıkla ve "new folder" seç. Daha sonra burada "sdk" yaz ve "sdk" üzerine tıkla daha sonra "next" ve "finish" tıkla. Bu süreçte tüm kelimeleri tam olarak ve İngilizce karakterlerle yazmaya dikkat et.

11. Android-Studio da "open existing project" tıkla ve daha sonra daha önce react-native projeni koymuş olduğun klasörü seç.

12. Android-Studio alt kısımda bir hata mesajı göreceksin ve bu mesajın üzerine tıkladığında sağ tarafta "install missing sdk packages" yazan mavi bir link göreceksin, bu mavi linke tıkla ve eksik paketleri indir.

13. Android-Studio üst çubuğunda "Tools/Avd Manager" tıkla ve "create virtual device" seç.

14. Burada bir cihaz seç ve bir sonraki ekranda "Nougat" sistemi seçip indir. Daha sonra "play" butonuna tıkla ve Emulatoru başlat.

15. Windows arama çubuğuna git ve buraya "System Settings" yazıp buna tıkla, daha sonra çıkan ekranda 'View Advanced System Settings" seçeneğine tıkla ve ondan sonra da "Advanced" seçeneğine tıkla.

16. Advanced tabinde "Environment Variables" butonuna tıkla, burada "new" üzerine tıkla. Ve acılan pencerede variable name kısmına tam olarak "JAVA_HOME" yaz. Eğer "JAVA_HOME" adında daha önceden oluşturulmuş bir değişken varsa tekrar oluşturmak zorunda değilsin. Burada variable value olarak "browse directory" butonuna tıkla. Burada "This PC/C Drive/program files/java/jdk-12" seç "Okay" tıkla.

17. Değişken isimleri arasında "PATH" adında bir değişken olmalı buna tıkla ve "edit" seç ve bir sonraki pencerede "new" üzerine tıkla ve buraya Android-Studio yu indirirken "sdk" klasörünü koyduğun yeri yaz. Bizim durumumuzda biz "D:\sdk\platform-tools" yazacağız. Bundan sonra "OK" üzerine tıkla ve "OK" basarak pencereleri kapat.

18. Terminalini kapat

19. Terminalini tekrar "Administrator (Yönetici)" olarak çalıştır.

20. Terminalde proje klasörüne git.

21. Proje klasöründe "react-native run-android" komutunu çalıştır. Eğer bu "bundler" başlatmazsa önce "react-native start" komutunu çalıştır.

NOT: Eğer emulatorunu çalıştırırken problem olursa lütfen aldığın hatanın bir ekran resmini ve react, reac-native, Android-Studio versiyonlarını bize gönder.
