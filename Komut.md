# Docker Komutları Hakkında Kısa Bişeyler

sık kullanılan bazı komutları buraya not aldım. Hem kendime hatırlatma olur.
---

## `docker pull`

Docker Hub'dan bir image'i indirir. Mesela `docker pull nginx` yazarsan nginx image'ini çeker. Tag belirtmezsen `latest` çeker ama bu her zaman en güncel olan değil dikkat!

> Örnek:  
`docker pull ubuntu:20.04`

---

## `docker images`

Sistemde yüklü olan docker image'leri listeler.  
Repository ismi, tag'i, image ID'si ve boyutu gibi bilgiler gösterilir.

> Küçük not: çok fazla image varsa `docker image prune` ile temizlik yapmak iyi olabilir ama dikkatli ol siler 🧹

---

## `docker exec`

Çalışan bir container içinde komut çalıştırmak için kullanılır.  
Genelde debug için ya da içine girip bakmak için kullanılır.

> Örnek:  
`docker exec -it my_container bash`  
Bu komut sayesinde container'ın içine terminalden girmiş oluyorsun.

---

## `docker stop`

Bir containerı durdurur.  
Durdurma işlemi gracefull olur yani servislerin kapanmasına izin verir.

> Örnek:  
`docker stop nginx_container`

---

## `docker rm`

Container silmek için kullanılır. Ama önce durdurulmuş olması gerekir yoksa çalışırken silemezsin.  
Container'ı sildikten sonra onun verilerine ulaşılamaz eğer volume vs bağlı değilse.

---

## `docker volume`

Docker volume'ları yönetmek için kullanılır. Volume'lar container silinse bile verinin kaybolmaması için kullanılır.  
Baya hayat kurtarır, özellikle database containerlarında.

> Örnek:  
`docker volume create my_volume`  
`docker volume ls`  
`docker volume rm my_volume`

---

## Ekstra Notlarım

- `docker ps` → çalışan container'ları gösterir  
- `docker ps -a` → çalışan + durmuş tüm containerları listeler  
- `docker logs` → container loglarını görmenizi sağlar  
- `docker-compose` → birden fazla containerı tek bir dosyada yönetmey  

---

Biraz karışık oldu belki ama iş görür 😉
