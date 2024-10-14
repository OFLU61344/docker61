
# Docker File ile mySQL çalıştırmak

### 1. adım : Docker'ı kurmak

docker file ile mysql çalıştırmadan önce docker'ın kurulu olduğundan emin olun


### 2. adım MySQL imajını çekmek

Docker hub'dan mySQL imajını terminalde kullanıyoruz

`docker pull mysql`,

bu komutla MySql imajları son sürümü ile indirilecek.

eğer başarı ile imajı çekerse  terminale docker images yazıp MySql'in image id'sini görebilirsiniz.


### 3. adım :  MySQL'i çalıştırmak.

MySql'i çalıştırmak için alttaki kodu yazın

`docker run --name='my_sql_container' -d -p 3306:3306 mysql server`

isterseniz docker ps yazarak çalışan docker konteynerlarını görebilirsiniz
