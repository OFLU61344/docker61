### Docker imajını nexus'a geçimenin farklı yolları var bunlardan birkaçı:
**Docker Push Komutu:** ile Docker imajınızı Nexus'a doğrudan Docker komutları kullanarak aktarabilirsiniz. Öncelikle Docker imajınızı oluşturun veya alın. Daha sonra bu imajı Nexus Docker Repository'sine yüklemek için `docker push` komutunu kullanabilirsiniz. Örneğin:
    
    bashCopy code
    
    `docker push nexus-url/repository-name/image-name:tag` 
    
    Nexus URL'si ve repository adını ve imaj adını ve etiketini kendi değerlerinizle değiştirmeniz gerekmektedir.


**Nexus CLI Kullanarak:** Nexus, Nexus CLI gibi araçlar sağlar. Bu araçları kullanarak Docker imajlarınızı Nexus'a yükleyebilirsiniz. Nexus CLI kullanarak öncelikle Nexus'a giriş yapmanız, ardından Docker imajınızı yüklemeniz gerekir. Bu yöntem, belirli senaryolarda daha fazla esneklik sunabilir.

**Jenkins veya diğer CI/CD Araçları ile Entegre Etme:** Eğer bir CI/CD (Continuous Integration/Continuous Deployment) aracı kullanıyorsanız, Docker imajınızı Nexus'a entegre edebilirsiniz. Örneğin, Jenkins gibi bir araçla Docker imajınızı oluşturduktan sonra, Jenkins pipeline veya job'ları aracılığıyla bu imajı Nexus'a yükleyebilirsiniz.


Docker imajını komut satırından aşağıdaki gibi gönderebilirsiniz:

-   docker tag <url_of_docker_registry>/image_name:image_tag
-   docker login -u username -p paswword <url_of_docker_registry>
-   docker push <url_of_docker_registry>/image_name:image_tag
-   
docker imajını Jenkins aracılığı ile push'layabilirsiniz

Download CloudBees Docker Build and Publish plugin.

 Manage Jenkins'e gidin oradan Manage Plugins'e tıklayın burdanda Available'a tıklayın (CloudBees Docker Build and Publish plugin'ini bulun) restartlamadan indirin.

Jenkins'in job configurasyonunda "build step as docker build and publish'e" tıklayın.
-   Repository ismi : İstediğiniz Repository ismi.
-   Tag : Docker image'inizi taglayın.
-   Docker registry URL : -   Docker kayıt URL'si: nexus OSS'de barındırılan docker kayıt defterinizin URL'si.
-   Registry credentials : docker kayıt defteriniz için kimlik bilgileri.
