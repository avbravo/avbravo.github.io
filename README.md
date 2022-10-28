## Avbravo



### Jmoordb Stack

Jmoordb Stack es el conjunto de Apis Java para el desarrollo de aplicaciones NoSQL orientado a Jakarta EE y Microprofile.


[Jmoordb Stack Book ](https://avbravo.gitbooks.io/stack-jmoordb/content/)

![Jmoordb Stack](https://i.postimg.cc/qv6rr5nS/jmoordb-stack.png)


Esta orientado a 
[JakartaEE ](https://jakarta.ee/)


Solo necesitas agregar al archivo pom.xml

```java
   <repositories>
        <repository>
            <id>jitpack.io</id>
            <url>https://jitpack.io</url>
        </repository>
    </repositories>
```


##Apis

### Jmoordb-core

```xml
	<dependency>
	    <groupId>com.github.avbravo</groupId>
	    <artifactId>jmoordb-core-processor</artifactId>
	    <version>1.0.7</version>
	</dependency>
 
### Jmoordb 

Jmoordb es un API para manejo de bases de datos NoSQL desde Java

Documentaciòn [jmoordb](https://app.gitbook.com/@avbravo-2/s/jmoordb/) 

## Jmoordb 2.5.4 (Microprofile)
```java
 <dependency>
          <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordb</artifactId>
            <version>2.5.4</version>
 </dependency>
```
Apartir de la versión 2.5 de Jmoordb se implementa el uso de Microprofile config oara indicar la conexión a la base de datos

Solo necesita agregar Define el uri de conexion al atributo mongodb.uri en el archivo microprofile-config.properties
```
Atlas
mongodb.uri=mongodb+srv://user:password@mogodbAtlas

Local

mongodb.uri=mongodb://localhost:27017
```

---
## jmoordb-core-quarkus

```xml

        <dependency>
	    <groupId>com.github.avbravo</groupId>
	    <artifactId>jmoordb-core-processor-quarkus</artifactId>
	    <version>0.1</version>
	</dependency>

```

---

## Jmoorb 2.3 (Legacy)


```java
  <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordb</artifactId>
            <version>2.3</version>
        </dependency>
```
Para versiones hasta 2.3 aun no tienen soporte para Microprofile,  en esas versiones era necesario indicar la conexión medianta la clase JmoordbConnection.

#### Conexiòn el init() de la clase principal

```java
@PostConstruct
    public void init() {
                    JmoordbConnection  jmoordbConnection = new JmoordbConnection.Builder()
                    .withSecurity(false)                  
                    .withDatabase("mydatabase")
                    .withHost("")
                    .withPort(0)
                    .withUsername("")
                    .withPassword(password)
                    .build();
    }
```


#### Conexiòn con MongoDBAtlas

```java
@PostConstruct
    public void init() {
                    JmoordbConnection  jmoordbConnection = new JmoordbConnection.Builder()
                    .wihtUrl("mongodb:srv://<user>:<password>@<cluster>/<basedatos>)
                    .build();
    }
```




#### Conexiòn con Microservices

```java
@ApplicationPath("resources")
public class JakartaRestConfiguration extends Application {
    @Override
    public Set<Class<?>> getClasses() {
        Set<Class<?>> resources = new java.util.HashSet<>();
        try {
            JmoordbConnection jmc = new JmoordbConnection.Builder()
                    .withSecurity(false)
                    .withDatabase("mydatabase")
                    .withHost("")
                    .withPort(0)
                    .withUsername("")
                    .withPassword("")
                    .build();
        } catch (Exception e) {
            System.out.println("Error " + e.getLocalizedMessage());
        }

        return resources;
    }
}
```



#### Configuracion
```java
JmoordbConfiguration jmc = new JmoordbConfiguration.Builder()
                    .withSpanish(true)                  
                    .withRepositoryRevisionHistory(revisionHistoryRepository)
                    .withRevisionHistoryServices(revisionHistoryServices)
                    .withRevisionSave(true)
                    .withUsername(username)
                    .build();
		     JmoordbContext.put("_userLogged", usuario);
```

### jmoordbannotations

- Api que se usa en el cliente y que solo define las annotaciones y utilidades. 
- No ofrece las apis para comunicarse con bases de datos nosql
- No soporta operaciones sobre bases de datos
- Se usa en los clientes generalmente Front-End
- Permite copiar los model o entity de un server y usarlos en el front-end
```java
<dependency>
	    <groupId>com.github.avbravo</groupId>
	    <artifactId>jmoordbannotations</artifactId>
	    <version>1.0</version>
</dependency>
```


### Jmoordbmodel 

Jmoordbmodel degine los model/entity que se usan para integrarse con multiples microservices

Documentaciòn [jmoordb](https://app.gitbook.com/@avbravo-2/s/jmoordb/) 

```java
  <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbmodel</artifactId>
            <version>0.11</version>
        </dependency>
```
### Jmoordbfaces (Jakarta EE 9.0 +)

Jmoordbjsf genera componentes Jakarta Server Faces
Requiere: Jakarta EE 9.0+


```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbfacesf</artifactId>
            <version>1.0</version>
        </
```


### Jmoordbjsf (Old Versiçn) Java Enterprise Edition 7.8

Jmoordbjsf genera componentes Java Server Faces

Documentaciòn [jmoordbjsf](https://avbravo.gitbooks.io/jmoordbjsf//content/) 

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbjsf</artifactId>
            <version>2.0.1</version>
        </dependency>
```

### Jmoordbutils for Jakarta EE 9-0 +

Utilidades

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbutils</artifactId>
            <version>3.3</version>
        </dependency>
```

### Jmoordbutils(Old Version) for Java Enterprise Edition 7,8.

Utilidades

```java
 <dependency>
            <groupId>com.github.avbravo</groupId>
            <artifactId>jmoordbutils</artifactId>
            <version>2.16.2</version>
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
            <version>0.3</version>
        </dependency>
```



### Jmoordbbootfacespatch

Genera un parche para bootfaces que consiste en corregir el error en el que no mostraba los componentes de Bootfaces al iniciar algunas versiones de GlassFish o Payara



```java
 <dependency>
	    <groupId>com.github.avbravo</groupId>
	    <artifactId>jmoordbbootfacespatch</artifactId>
	    <version>0.1</version>
	</dependency>
```


### jmoordbarchetypeejb

Es un archetype crea un proyecto ejb basado en jmoordb con dos entitys Rol/Usuario.
Genera:
Entity
Repository
Services
DataModel
Converter
Documentaciòn [jmoordbarchetypeejb](https://github.com/avbravo/jmoordbarchetypeejb) 

```java
 Pasos:
 1. Clonar el proyecto
 2. Crear el archetype
 3. Crear el proyecto a partir del archetype
 En el repositorio github estan las instrucciones
```

### crud
https://github.com/avbravo/crud
Es un archetype crea un proyecto crud  basado en jmoordbjsd que se comunica con el proyecto ejb con dos entitys Rol/Usuario.
Genera:
Template
paginas
index.xhtml
login.xhtml
list.xhtml
view.xhtml
new.xhtml
messages.propeties
controller
securiry
Documentaciòn [jmmoordbtaller](https://app.gitbook.com/@avbravo-2/s/jmoordbtaller/untitled) 

```java
 Pasos:
 1. Clonar el proyecto
 2. Crear el archetype
 3. Crear el proyecto a partir del archetype
 En el repositorio github estan las instrucciones
 
 Clonamos el proyecto
Creamos una carpeta
mkdir template
cd template
clonamos el proyecto
git clone https://github.com/avbravo/crud.git
Entramos al directorio crud
cd crud

Ejecutar
mvn archetype:create-from-project
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


### Jmoordbadminfaces

Es un archetype que empaqueta la configuraciòn basica de  adminfaces template con dependencias de jmoordb para crear rapidamente la aplicacionJava EE
Documentaciòn [Jmoordbadminfaces](https://github.com/avbravo/jmoordbadminfaces) 

```java
 Pasos:
 1. Clonar el proyecto
 2. Crear el archetype
 3. Crear el proyecto a partir del archetype
 En el repositorio github estan las instrucciones
 
```

### adminfacesarchetype

adminfacesarchetype empaqueta todo el demo de adminfaces template con dependencias de jmoordb para crear rapidamente la aplicacionJava EE
Documentaciòn [adminfacesadminfacesarchetype](https://github.com/avbravo/adminfacesarchetype) 

```java
 Pasos:
 1. Clonar el proyecto
 2. Crear el archetype
 3. Crear el proyecto a partir del archetype
 En el repositorio github estan las instrucciones
 
```





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








### Support or Contact

Aristides Villareal Bravo [avbravo@gmail.com](avbravo@gmail.com) 

Editar sitio [editor on GitHub](https://github.com/avbravo/avbravo.github.io/edit/master/README.md) 

