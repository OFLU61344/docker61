
# Docker Compose ile PostreSQL Nasıl Çalıştırılır.


### 1. Adım : Docker'ı indirmek

Docker compose'u kurup kullanmadan önce Docker'ın sistemimizde indirili olduğundan emin olmalıyız.

### 2. Adım: Docker Compose İndirmek

Bir PostgreSQL konteynır'ı kullanmak için docker compose dosyası oluşturmamız gerekiyor sisteminizin herhangi bir terminalinde bu dosyayı oluşturabilirsiniz.
ismi "docker-compose.yml" olacak bir dosya oluşturun ve içine alttaki satırları işleyin

```
version:  '3.9'  
  
services:  
postgres:  
image:  postgres:14-alpine  
ports:  
-  5432:5432  
volumes:  
-  ~/apps/postgres:/var/lib/postgresql/data  
environment:  
-  POSTGRES_PASSWORD= "şifreniz" 
-  POSTGRES_USER= "kullanıcı adınız"
-  POSTGRES_DB= "Veri Tabanı Adınız"
```


### 3. Adım: PostgreSQL Konteynerini başlatın

PostgreSQL Konteynerini çalıştırmak için terminalinizde dosyanın bulunduğu dizine gidin ve aşağıdaki komutu çalıştırın: 

`Docker-compose up -d` 
