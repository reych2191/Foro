# ForoHub

ForoHub es una API REST diseñada para gestionar tópicos en un foro, permitiendo a los usuarios crear, leer, actualizar y eliminar tópicos. Este proyecto está desarrollado con Spring Boot, utilizando una base de datos H2 para el almacenamiento de datos y Spring Security para la autenticación y autorización.

## Descripción del Proyecto

Un foro es un espacio de colaboración donde los participantes pueden plantear preguntas y recibir respuestas sobre diferentes tópicos. ForoHub simula esta funcionalidad en el backend, ofreciendo una API completa para realizar operaciones CRUD sobre los tópicos.

### Funcionalidades

1. **Crear Tópicos:** Permite a los usuarios crear nuevos tópicos en el foro.
2. **Leer Tópicos:** Permite a los usuarios listar todos los tópicos existentes o consultar un tópico específico.
3. **Actualizar Tópicos:** Permite a los usuarios modificar un tópico existente.
4. **Eliminar Tópicos:** Permite a los usuarios eliminar un tópico del foro.

## Tecnologías Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **Spring Security**
- **H2 Database**
- **Maven**

## Configuración e Instalación

### Prerrequisitos

- Java 17
- Maven

### Clonar el Repositorio

```bash
git clone https://github.com/tuusuario/ForoHub.git
cd ForoHub
Compilar e Instalar Dependencias
bash
Copy code
mvn clean install
Configuración de la Base de Datos
El proyecto utiliza H2 Database para el desarrollo. La configuración se encuentra en src/main/resources/application.properties.

properties
Copy code
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
Ejecución de la Aplicación
Para ejecutar la aplicación, usa el siguiente comando:

bash
Copy code
mvn spring-boot:run
La aplicación estará disponible en http://localhost:8080.

Uso de la API
Endpoints
Crear un nuevo tópico
URL: POST /topics
Request Body:
json
Copy code
{
  "title": "Nuevo Tópico",
  "message": "Este es el contenido del nuevo tópico"
}
Respuesta Exitosa: 201 Created
Listar todos los tópicos
URL: GET /topics
Respuesta Exitosa: 200 OK
Response Body:
json
Copy code
[
  {
    "id": 1,
    "title": "Tópico 1",
    "message": "Contenido del tópico 1"
  },
  ...
]
Consultar un tópico específico
URL: GET /topics/{id}
Respuesta Exitosa: 200 OK
Response Body:
json
Copy code
{
  "id": 1,
  "title": "Tópico 1",
  "message": "Contenido del tópico 1"
}
Actualizar un tópico
URL: PUT /topics/{id}
Request Body:
json
Copy code
{
  "title": "Tópico Actualizado",
  "message": "Este es el contenido actualizado del tópico"
}
Respuesta Exitosa: 200 OK
Eliminar un tópico
URL: DELETE /topics/{id}
Respuesta Exitosa: 204 No Content
Autenticación
ForoHub utiliza autenticación básica. Las credenciales predeterminadas son:

Username: user
Password: password
Para probar la autenticación en Postman:

Ve a la pestaña Authorization.
Selecciona el tipo Basic Auth.
Introduce el Username y Password proporcionados.
Seguridad
La configuración de seguridad se encuentra en src/main/java/com/example/forohub/SecurityConfig.java
