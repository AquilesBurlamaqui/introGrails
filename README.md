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

generate-controller divulga.Espaco

run-app







