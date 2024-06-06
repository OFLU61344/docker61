## Docker file nedir?

Docker file basit bir metin dosyasıdır. Dockerfile uygulama imajlarını oluşturmak için kullanılır.
Docker file gerekli işletim sistemi, kurulucak araçlar, database, uygulamanın çalışması için gerekli dosyalar ve kütüphaneleri içeren dosyadır. 

## Docker file nasıl oluşturulur?
### Docker file oluşturmanın çeşitli yolları vardır. Bunlar sırasıyla:

RUN: Belirtilen komutları image içerisinde çalıştırır.  
FROM: Kullanılacak sistem belirtilir.  
COPY: Belirtilen dosyaları image içerisinde belirlenen hedefe kopyalar.  
LABEL: Image dosyasına aranabilir meta tagları eklememizi sağlar.  
WORKDIR: Sonrasında gelen komutları verilen klasör içerisindeymiş gibi çalıştırır.  
EXPOSE: Container’ın docker içinde çalışacağı port adresi belirlenir.  
ENV: Image içerisine dışarıdan veri girileceği zaman kullanılır.
CMD: İlk önce çağrılır. Çalışma sırasını düzenler. İçine yazılan komut ve parametreleri çalıştırır.  
