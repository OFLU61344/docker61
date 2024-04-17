 **Docker Push Komutu:** ile Docker imajınızı Nexus'a doğrudan Docker komutları kullanarak aktarabilirsiniz. 
 Öncelikle Docker imajınızı oluşturun veya alın. Daha sonra bu imajı Nexus Docker Repository'sine yüklemek için `docker push` komutunu kullanabilirsiniz. Örneğin:
    
    bashCopy code
    
    `docker push nexus-url/repository-name/image-name:tag` 
    
    Nexus URL'si ve repository adını ve imaj adını ve etiketini kendi değerlerinizle değiştirmeniz gerekmektedir.


Yada, **Nexus CLI Kullanarak:** Nexus, Nexus CLI gibi araçlar sağlar. 
Bu araçları kullanarak Docker imajlarınızı Nexus'a yükleyebilirsiniz. 
Nexus CLI kullanarak öncelikle Nexus'a giriş yapmanız, ardından Docker imajınızı yüklemeniz gerekir.
Bu yöntem, belirli senaryolarda daha fazla esneklik sunabilir.

Yada, **Jenkins veya diğer CI/CD Araçları ile Entegre Etme:** Eğer bir CI/CD (Continuous Integration/Continuous Deployment) aracı kullanıyorsanız,
Docker imajınızı Nexus'a entegre edebilirsiniz. Örneğin, Jenkins gibi bir araçla Docker imajınızı oluşturduktan sonra,
Jenkins pipeline veya job'ları aracılığıyla bu imajı Nexus'a yükleyebilirsiniz.
