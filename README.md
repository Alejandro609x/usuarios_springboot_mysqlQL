# usuarios-spring-boot

## 📖 Descripción del Proyecto

Este proyecto consiste en una aplicación REST desarrollada con **Spring Boot**, utilizando **MySQL** como base de datos. Proporciona endpoints REST para realizar operaciones CRUD (crear, leer, actualizar y eliminar) sobre usuarios.

---

## 🛠️ Estructura del Proyecto

### 📂 src/main/java

- **controller:** Maneja solicitudes HTTP mediante endpoints REST.
- **exception:** Contiene excepciones personalizadas para manejo de errores.
- **model:** Define entidades JPA que representan tablas de la base de datos.
- **repository:** Interfaces y clases que interactúan con la base de datos.
- **service:** Implementa la lógica de negocio.
- **UsuariosApplication.java:** Clase principal que inicia la aplicación.

### 📂 src/main/resources

- **application.properties:** Archivo de configuración para la aplicación (base de datos, puerto, etc.).

---

## 🔧 Configuración de la base de datos

- **Base de datos:** `clientes`
- **Tabla:** `usuarios`

```sql
CREATE TABLE usuarios(
    id bigint NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nombre varchar(100) DEFAULT NULL,
    apellido varchar(100) DEFAULT NULL,
    email varchar(100) DEFAULT NULL
);
```

---

## 📌 Configuración (`application.properties`)

```properties
spring.application.name=usuarios
spring.datasource.username=TU_USUARIO
spring.datasource.password=TU_CONTRASEÑA
spring.datasource.url=TU_URL
server.servlet.context-path=/users
```

---

## 🗂️ Dependencias (`pom.xml`)

- `spring-boot-starter-data-jpa`: Gestión de persistencia con JPA (Hibernate).
- `spring-boot-starter-web`: Desarrollo de servicios REST.
- `mysql-connector-java`: Conexión con base de datos MySQL.
- `springdoc-openapi-starter-webmvc-ui`: Documentación automática (Swagger UI).
- `spring-boot-starter-test`: Para pruebas unitarias e integración.

---

## 🚀 Endpoints REST

| Operación            | Método HTTP | URL                      |
|----------------------|-------------|--------------------------|
| Obtener usuarios     | GET         | `/users/users`           |
| Crear usuario        | POST        | `/users/create`          |
| Actualizar usuario   | PUT         | `/users/update`          |
| Obtener usuario por ID | GET       | `/users/users/{id}`      |
| Eliminar usuario     | DELETE      | `/users/user/{id}`       |

---

## 📌 Clases destacadas

### UserController
Controlador REST para gestionar solicitudes HTTP.

### UserService
Servicio que contiene la lógica del negocio e interacción con el repositorio.

### User
Entidad JPA que representa un usuario en la base de datos.

### NotFoundException
Excepción personalizada para recursos no encontrados (devuelve HTTP 404).

---

## ⚙️ Ejecución del proyecto

Para ejecutar la aplicación:

```
mvn clean install
mvn spring-boot:run
```

La aplicación estará disponible en:
```
http://localhost:8080/users
```

Documentación API Swagger UI disponible en:
```
http://localhost:8080/users/swagger-ui.html
```

---

## 📚 Tecnologías utilizadas

- Java 17
- Spring Boot 3.3.9
- MySQL 8.0.33
- Maven
- IntelliJ IDEA
