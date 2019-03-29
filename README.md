## Avbravo



### Jmoordb Stack

Jmoordb Stack es el conjunto de Apis Java para el desarrollo de aplicaciones NoSQL orientado a Jakarta EE y Microprofile.


[Jmoordb Stack Book ](https://avbravo.gitbooks.io/stack-jmoordb/content/)

![Jmoordb Stack](https://i.postimg.cc/ydX0ZW22/jmoordb-stack-1.png)


Esta orientado a 
[JakartaEE ](https://jakarta.ee/)


Solo necesitas agregar al archivo pom.xml

```java
   <repository>
     <id>jitpack.io</id>
     <url>https://jitpack.io</url>
    </repository>
```

##Apis

### Jmoordb 

Jmoordb es un API para manejo de bases de datos NoSQL desde Java

Documentaciòn [jmoordb](https://avbravo.gitbooks.io/jmoordb/content/) 

```java
  <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordb</artifactId>
            <version>0.24</version>
        </dependency>
```

#### Conexiòn el init() de la clase principal

```java
@PostConstruct
    public void init() {
                    JmoordbConnection  jmoordbConnection = new JmoordbConnection.Builder()
                    .withSecurity(false)                  
                    .withDatabase("")
                    .withHost("")
                    .withPort(0)
                    .withUsername("")
                    .withPassword(password)
                    .build();
    }
```


#### Configuracion
```java
JmoordbConfiguration jmc = new JmoordbConfiguration.Builder()
                    .withSpanish(true)                  
                    .withRepositoryRevisionHistory(revisionHistoryStoreejbRepository)
                    .withRevisionHistoryServices(revisionHistoryServices)
                    .withRevisionSave(true)
                    .withUsername(username)
                    .build();
		     JmoordbContext.put("_userLogged", usuario);
```


### Jmoordbjsf

Jmoordbjsf genera componentes Java Server Faces

Documentaciòn [jmoordbjsf](https://avbravo.gitbooks.io/jmoordbjsf//content/) 

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbjsf</artifactId>
            <version>0.6</version>
        </dependency>
```


### Jmoordbaudit

Auditoria y Test Progresivos

Documentaciòn [jmoordbunit](https://avbravo.gitbooks.io/jmoordbunit/content/) 

```java
 <dependency>
	    <groupId>com.github.avbravo</groupId>
	    <artifactId>jmoordbaudit</artifactId>
	    <version>1.1</version>
	</dependency>
```



### Jmoordbutils

Utilidades

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbutils</artifactId>
            <version>0.2.2</version>
        </dependency>
```




### Jmoordbsecurity

Seguridad aplicaciones Jakarta EE

*En migracion

Documentaciòn [avbravosecurity](https://avbravo.gitbooks.io/avrbavosecurity/content/) 

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbsecurity</artifactId>
            <version>0.1</version>
        </dependency>
```



### Jmoordbwizard
Generador de aplicación jakarta ee Standalone.

Es una aplicacion web para crear aplicaciones JakartaEE con Jmoordb



### Jmoordbreport
Plugin para generar reportes Jaspertreport desde NetBeans IDE


Descargas [NetBeans plugin](http://plugins.netbeans.org/plugin/75519/?show=true) 


### Jmoordbbackup
Plugin para generar backup/restaurar bases de datos NoSQL desde NetBeans IDE

Descargas [NetBeans plugin](http://plugins.netbeans.org/plugin/75520/?show=true) 


### jmoordbjsfgenerator
Plugin para NetBeans que genera aplicaciones Jakarta EE

### JMoordbejbgenerator
Plugin para NetBeans que genera un proyecto ejb para JMoordb


### Libros Online

[Jmoordb Stack](https://avbravo.gitbooks.io/stack-jmoordb/content/)  

[Jmoordb](https://avbravo.gitbooks.io/jmoordb/content/)  

[Jmoordb CookBook](https://avbravo.gitbooks.io/jmoordb-cookbook/content/) 

[Jmoordb Core](https://avbravo.gitbooks.io/jmoordb-code/content/) 

[jmoordb unit](https://avbravo.gitbooks.io/jmoordbunit/content/)  

[avbravosecurity](https://avbravo.gitbooks.io/avrbavosecurity/content/)   

[avbravoutil](https://avbravo.gitbooks.io/avbravoiutil/content/)    

[reportwizard](https://avbravo.gitbooks.io/reportwizard/content/) 
  
[wizardjmoordb](https://avbravo.gitbooks.io/wizardjmoordb/content/) 

[Trucos Jakarta EE](https://avbravo.gitbooks.io/trucosjakartaee/content/) 

[Development CookBook](https://avbravo.gitbooks.io/developmentcookbook/content/) 






# Otros NetBeans Plugins


[DataClassG Genera ORM para SQL ](http://plugins.netbeans.org/plugin/39424/?show=true)  

[DBackRestore  Backup and Restore for MySQL in GNU/Linux](http://plugins.netbeans.org/plugin/42928/?show=true) 

[javscazGChat Chat Client for Gmail.](http://plugins.netbeans.org/plugin/39307/?show=true) 

[JSFGenerator Crea Java Server Faces Pages para DataClassG](http://plugins.netbeans.org/plugin/39439/?show=true) 

[mback Backup/Restore MongoDB](http://plugins.netbeans.org/plugin/74890/?show=true)        

[reportwizard Generador de Reportes](http://plugins.netbeans.org/plugin/74252/?show=true) 






# Technical Review in Packt Publising

1. [PrimeFaces Blueprints ](https://www.packtpub.com/application-development/primefaces-blueprints) 

2. [PrimeFaces Theme Development ](https://www.packtpub.com/web-development/primefaces-theme-development) 

3. [Apache Hive Cookbook ](https://www.packtpub.com/big-data-and-business-intelligence/apache-hive-cookbook) 

4. [Dart By Example ](https://www.packtpub.com/web-development/dart-example) 

5. [Java EE Development with Eclipse - Second Edition](https://www.packtpub.com/application-development/java-ee-development-eclipse-second-edition) 

6. [Express.js Blueprints](https://www.packtpub.com/web-development/expressjs-blueprints) 

7. [PrimeFaces Cookbook - Second Edition](https://www.packtpub.com/application-development/primefaces-cookbook-second-edition) 

8. [Mastering Google App Engine](https://www.packtpub.com/virtualization-and-cloud/mastering-google-app-engine) 


9. [Java 9 Cookbook]() 

10. [Angular UI Development with PrimeNG](https://www.packtpub.com/web-development/angular-ui-development-primeng) 

11. [Java 9 High Performance](https://www.packtpub.com/application-development/java-9-high-performance) 

12. [Design Patterns and Best Practices in Java](https://www.packtpub.com/application-development/design-patterns-and-best-practices-java) 

13. [Introduction to Programming](https://www.packtpub.com/application-development/introduction-programming) 

14. [Java 9 Cookbook Solutions for Modular, Functional, Reactive, and Multithreaded programming](https://www.amazon.com/Java-Cookbook-Functional-Multithreaded-programming/dp/1786461404) 

15. [Mastering Java EE 8 Application Development](https://www.packtpub.com/application-development/mastering-java-ee-8-application-development) 

16. [Java 11 Cookbook - Second Edition](https://www.packtpub.com/application-development/java-11-cookbook-second-edition) 

17. [Java Projects - Second Edition](https://www.packtpub.com/application-development/java-projects-second-edition) 
  
18. [Java EE 8 Microservices](https://www.packtpub.com/application-development/java-ee-8-microservices) 

19. [Mastering Microservices with Java 11](https://www.packtpub.com/application-development/mastering-microservices-java-third-edition)




### Support or Contact

Aristides Villareal Bravo [avbravo@gmail.com](avbravo@gmail.com) 

Editar sitio [editor on GitHub](https://github.com/avbravo/avbravo.github.io/edit/master/README.md) 

