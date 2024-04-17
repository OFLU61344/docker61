# Docker image nasıl oluşturulur.

1. Docker file oluşturulalım.
````
FROM nginx 
ENV AUTHOR=DockerEnv 
WORKDIR /usr/share/nginx/html
COPY Color_docker.html /usr/share/nginx/html
CMD cd /usr/share/nginx/html && sed -e s/DockerEnv/"$AUTHOR"/ Color_docker.html > 
index.html ; nginx -g 'daemon off;'
````

2. Background değişikliği yapabileceğimiz bir html dosyası hazırlayalım.

```
<html>  
<head><style>  
body {background-color: DockerEnv;}  
</style></head>  
<body></body>  
</html>
```
3. Klasör içinde terminal açıp, build komutunu girerek image dosyasını oluşturalım.
```
$ Docker build -t myimage .
```
![image](https://github.com/OFLU61344/docker61/assets/118263276/25dc8b4d-25f7-4d7c-b5f8-904e397f3f93)

Görüldüğü üzere Docker File içerisindeki tüm adımlar tek tek gerçekleşti ve “myimage” adında bir Docker image oluşturmuş olduk.

4. Docker image, run komutu kullanılarak container haline getirilir.
```
$ Docker run -d -p 8880:80 -e AUTHOR=”blue” myimage
```
