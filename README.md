# Introdução ao Grails

Bem vindos a minha página tutorial sobre Grails.

## Grails.

### Instalação via windows

#### 1 Instalar o https://www.cygwin.com/
#### 2 Instalar o JDK https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html


### Criando API Rest

grails create-app divulga --profile=rest-api

cd divulga

grails

create-domain-class Espaco

##### Espaco.groovy
~~~ java
package divulga

class Espaco {
	String nome
	String descricao

    static constraints = {
    }
}
~~~
##### Criando os controllers
generate-controller divulga.Espaco

##### executando a aplicaço
run-app

##### testando a api rest
curl -i -H "Accept: application/json" localhost:8080/espaco


## Instalando o Spring Security

##### build.gradle
dependencies {
   ...
   compile 'org.grails.plugins:spring-security-core:3.2.3'
   ...

### executando o script para criar usuario(User) e os papeis(Role)
grails s2-quickstart divulga User Role


##### Bootstrap.groovy
~~~ Java
package divulga

class BootStrap {

    def init = { servletContext ->
    	def role1 = new Role(authority:"ROLE_ADMIN").save flush:true
        def user1 = new User(username:"admin",password:"admin").save flush:true
    	UserRole.create(user1,role1)

    	def role2 = new Role(authority:"ROLE_USER").save flush:true
		def user2 = new User(username:"user",password:"user").save flush:true
		UserRole.create(user2,role2)
    }
    def destroy = {
    }
}

~~~

