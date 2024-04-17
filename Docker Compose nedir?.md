Compose multi-container docker uygulamaları tanımlamak ve çalıştırmak için kullanılan bir araçtır. Compose ile, YAML dosyası kullanarak uygulama servislerini konfigure edebiliriz. Daha sonra bir komut ile yaptığımız konfigürasyonları bütün servisleri oluşturarak başlatabiliriz.

Ayrıca compose; production, staging, development, test ve CI workflowlarında çalışmaktadır.

### **3 adımda compose kullanmak**

**1-**  Dockerfile ile uygulama environment tanımla. Böylece her yerde tekrardan üretilebilir.

**2-**  docker-compose.yml dosyasında uygulama içindeki servisleri tanımla. Böylece birbirlerinden izole bir ortamda çalışan servisler oluşturabiliriz.

**3-**  docker compose up komutunu çalıştır, compose uygulamamızı başlatıp çalıştıracaktır.

Örnek bir docker-compose.yml dosyası şu şekildedir:

![image](https://github.com/OFLU61344/docker61/assets/118263276/12761806-19f1-45e0-9a53-42d934d8168d)

**Compose uygulamanın tüm yaşam döngüsünü yönetmek için komutlara sahiptir:**

- Servisleri başlatma, durdurma ve yeniden ayağa kaldırma

- Çalışan servislerin durumunu izleme

**Compose’u efektif yapan özellikleri:**

_**-Single host üzerinde birden fazla izole edilmiş ortam**_

Compose ortamları birbirinden izole etmek için proje adı kullanır. Proje adı kullanımını farklı şekillerde yapılabilir:

- dev host üzerinde, single environmentın multiple kopyasını oluşturmak için.

- CI server üzerinde, yapıların birbirine karışmasını önlemek için proje adını unique olarak belirleyebilirsiniz.

-shared host ya da dev host üzerinde, aynı adları kullanan farklı projelerin birbirine karışmasını önlemek için.

_**-Containerlar oluşturulduğu zaman volume dataları saklar**_

Compose servisler tarafından kullanılan tüm volumeları saklar. docker compose up komutu çalıştığı zaman, eğer önceki çalıştırmalardan bir container bulursa, eski containerdan yeni containera verileri kopyalar. Böylece volume içinde oluşturduğumuz herhangi bir data kaybedilmez.

_**-Sadece yapılan değişiklikler için containerları yeniden oluşturur**_

Değişiklik olmayan bir servisi tekrardan başlattığımız zaman, compose halihazırdaki containerı yeniden kullanır. Yeniden kullanılan container demek kendi environmentımıza hızlıca değişiklik yapabiliriz.

### **Yaygın Kullanımlar**

**Development ortamları**

Yazılım geliştirirken, bir uygulamayı izole edilmiş bir ortamda çalıştırmak önemlidir. Compose bu ortamı oluşturmada kullanılabilir. Compose dosyası uygulamanın servis bağımlılıklarını konfigure etmede bir yol sunar. Compose command line aracı ile her bir bağımlılık için bir veya birçok container oluşturup çalıştırabiliriz. Bu özellikler ile birlikte, developerların projeye başlamsı için uygun bir ortam sağlar.

**Otomatize edilmiş test ortamları**

CI/CD süreçleri için önemli kısımlardan birisi de otomatiğe edilmiş testlerdir. e2e test, testlerin yürütüleceği bir ortam gerektirir. Compose test ekipleri için izole edilmiş test ortamları oluşturmak ve yok etmek için uygun bir yol sağlar. Bu ortamları yalnızca birkaç komut ile oluşturabilir ya da yok edebilirsiniz:

docker-compose up -d

./run_tests

docker-compose down


**Docker Compose Komutları**

**1.** docker compose up -d : **docker-compose.yml dosyasında yazdığımız servisler için containerları oluşturur ve başlatır.**

**2.** docker compose down : **dosyada yazılmış ve up komutuyla başlatılmış containerları durdurur ve kaldırır.**

**3.** docker compose build : **dosyada yazılmış containerları build etmek için kullanılır.**

**4.** docker compose config : **compose dosyasını görüntüler.**

**5.** docker compose images : **Dosyada yazılmış containerların kullandıkları imageları gösterir.**

**6.** docker compose start : **Oluşturulan containerları başlatır.**

**7.** docker compose stop : **Çalışan containerları durdurur.**

**8.** docker compose rm : **Durdurulan containerları siler.**

**9.** docker compose top : **Çalışan processleri listeler.**

**10.** docker-compose restart : **Tüm servisleri yeniden başlatır.**

 **11.** docker-compose restart <servis_adı> : **Belirli bir servisi yeniden başlatır.**

**12.** docker-compose up <servis_adı1> <servis_adı2> : **Birden fazla servisi yeniden başlatır.**

**13.** docker-compose stop <servis_adı> : **Servisi durdurur.**

**14.** docker-compose stop : **Tüm servisleri durdurur**

**15.** docker-compose rm <servis_adı> : **Servisi siler.**

**16.** docker-compose rm : **Tüm servisleri siler.**

**17.** docker-compose logs <servis_adı> : **Servis loglarını görüntüler.**

**18.**  docker-compose restart <servis_adı> : **Belirli bir servisi yeniden başlatır.**

**19.** docker-compose stop <servis_adı> : **Belirli bir servisin konteynerlarını durdurma.**

**20.** docker-compose ps : **Konteynerların durumunu görüntüleme:**

**21.** docker inspect $(docker-compose ps -q) | grep IPAddress : **Konteynerların IP adreslerini görüntüleme:**

**22.** docker-compose export : **Dışa aktarma (export) işlemi:**

**23.** docker-compose config > docker-compose.yml : **Çevrimdışı kullanım için YAML dosyası oluşturma:**

**24.** docker-compose pull : **Servis bağımlılıklarını yeniden yükleme:**

**25.** docker-compose config : **Docker Compose dosyasının doğruluğunu kontrol etme:** 

**26.** docker-compose build : **Docker Compose dosyasını yeniden yapılandırma:**

**27.** docker-compose down : **Tüm konteynerları durdurma ve kaldırma:**

**28.** docker-compose logs -f <servis_adı> : **Belirli bir servisin günlüğünü canlı olarak takip etme:**

**29.** docker-compose ps <servis_adı> : **Belirli bir servisin detaylı durumunu görüntüleme**

**30.** docker-compose exec <servis_adı> <_komut_> : **Belirli bir servisin özel bir komutunu çalıştırma:** 
