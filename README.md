# training-security-notes-api

Proyecto de ejemplo para formación sobre seguridad en aplicaciones web.

Basado en: [https://www.adictosaltrabajo.com/2012/07/30/spring-mvc-api-rest-oauth-2/](https://www.adictosaltrabajo.com/2012/07/30/spring-mvc-api-rest-oauth-2/)

#### Entorno

- Java 1.8
- Maven 3.5
- Tomcat 7
- MySQL

#### Compilación

`mvn clean install  -Dmaven.test.skip=true`

#### Ejecución

`mvn tomcat7:run -X -Dmaven.tomcat.port=8080`
 
## API Small Notes

API REST sin securizar que mantiene tabla de la aplicación Small Notes. El usuario conectado está mockeado para este estado inicial sin seguridad.

#### Prueba
	
Probar la aplicación sin seguridad accediendo a: `http://localhost:8080/smallNotes/v1/api/notes`

## Ejercicio

Securizar la API mediante configuración **Spring Security** aplicando **OAuth2**.

#### Acciones
	
- Añadir los filtros de securidad en `web.xml`.
- Crear configuración spring de seguridad OAuth2 y añadirla al spring context.
- Crear las clases OAuth2: 
	- `AccessConfirmationController`: Controller de gestión de las páginas de identificación
	- `UserApprovalHandler`: Token específico de tipo `TokenServicesUserApprovalHandler`.
- Añadir las anotaciones de seguridad de los endpoints de controllers.

Finalmente probar el acceso con una aplicación cliente que gestione la identificación del usuario mediante OAuth2. 

Para esto utilizaremos la aplicación web `training-security-notes-webapp`: 

[https://github.com/mazingergonzalez/training-security-notes-webapp](https://github.com/mazingergonzalez/training-security-notes-webapp)


