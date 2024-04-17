## Ubuntu 22.04'e nasıl docker kurulur.

Önce paket listemizi güncelleyelim.
````
sudo apt update
````

Daha sonra, paketlerin HTTPS üzerinden kullanılmasına izin veren birkaç önkoşul paketini yükleyin :
````
sudo apt install apt-transport-https ca-certificates curl software-properties-common
````

Ardından resmi Docker deposunun GPG anahtarını sisteminize ekleyin:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Docker deposunu APT kaynaklarına ekleyin:
````
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
````

Eklemenin tanınması için mevcut paket listenizi tekrar güncelleyin:
````
sudo apt update
````

Varsayılan Ubuntu deposu yerine Docker deposundan yükleme yapmak üzere olduğunuzdan emin olun:
````
apt-cache policy docker-ce
````

Docker'ın sürüm numarası farklı olsa da çıktıyı şu şekilde göreceksiniz:
