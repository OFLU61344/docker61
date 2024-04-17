Compose multi-container docker uygulamaları tanımlamak ve çalıştırmak için kullanılan bir araçtır. Compose ile, YAML dosyası kullanarak uygulama servislerini konfigure edebiliriz. Daha sonra bir komut ile yaptığımız konfigürasyonları bütün servisleri oluşturarak başlatabiliriz.

Ayrıca compose; production, staging, development, test ve CI workflowlarında çalışmaktadır.

### **3 adımda compose kullanmak**

**1-**  Dockerfile ile uygulama environment tanımla. Böylece her yerde tekrardan üretilebilir.

**2-**  docker-compose.yml dosyasında uygulama içindeki servisleri tanımla. Böylece birbirlerinden izole bir ortamda çalışan servisler oluşturabiliriz.

**3-**  docker compose up komutunu çalıştır, compose uygulamamızı başlatıp çalıştıracaktır.

Örnek bir docker-compose.yml dosyası şu şekildedir:

![image](https://github.com/OFLU61344/docker61/assets/118263276/12761806-19f1-45e0-9a53-42d934d8168d)

Compose uygulamanın tüm yaşam döngüsünü yönetmek için komutlara sahiptir:
- Servisleri başlatma, durdurma ve yeniden ayağa kaldırma
- Çalışan servislerin durumunu izleme
Compose’u efektif yapan özellikleri:
-Single host üzerinde birden fazla izole edilmiş ortam
Compose ortamları birbirinden izole etmek için proje adı kullanır. Proje adı kullanımını farklı şekillerde yapılabilir:
- dev host üzerinde, single environmentın multiple kopyasını oluşturmak için.
- CI server üzerinde, yapıların birbirine karışmasını önlemek için proje adını unique olarak belirleyebilirsiniz.
-shared host ya da dev host üzerinde, aynı adları kullanan farklı projelerin birbirine karışmasını önlemek için.
-Containerlar oluşturulduğu zaman volume dataları saklar
Compose servisler tarafından kullanılan tüm volumeları saklar. docker compose up komutu çalıştığı zaman, eğer önceki çalıştırmalardan bir container bulursa, eski containerdan yeni containera verileri kopyalar. Böylece volume içinde oluşturduğumuz herhangi bir data kaybedilmez.
-Sadece yapılan değişiklikler için containerları yeniden oluşturur
Değişiklik olmayan bir servisi tekrardan başlattığımız zaman, compose halihazırdaki containerı yeniden kullanır. Yeniden kullanılan container demek kendi environmentımıza hızlıca değişiklik yapabiliriz.
Yaygın Kullanımlar
Development ortamları
Yazılım geliştirirken, bir uygulamayı izole edilmiş bir ortamda çalıştırmak önemlidir. Compose bu ortamı oluşturmada kullanılabilir. Compose dosyası uygulamanın servis bağımlılıklarını konfigure etmede bir yol sunar. Compose command line aracı ile her bir bağımlılık için bir veya birçok container oluşturup çalıştırabiliriz. Bu özellikler ile birlikte, developerların projeye başlamsı için uygun bir ortam sağlar.
Otomatize edilmiş test ortamları
CI/CD süreçleri için önemli kısımlardan birisi de otomatiğe edilmiş testlerdir. e2e test, testlerin yürütüleceği bir ortam gerektirir. Compose test ekipleri için izole edilmiş test ortamları oluşturmak ve yok etmek için uygun bir yol sağlar. Bu ortamları yalnızca birkaç komut ile oluşturabilir ya da yok edebilirsiniz:
docker-compose up -d
./run_tests
docker-compose down
