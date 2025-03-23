usuarios-spring-boot

📖 Descripción del Proyecto

Este proyecto consiste en una aplicación REST desarrollada con Spring Boot, utilizando MySQL como base de datos. Proporciona endpoints REST para realizar operaciones CRUD (crear, leer, actualizar y eliminar) sobre usuarios.

🛠️ Estructura del Proyecto

📂 src/main/java

controller: Maneja solicitudes HTTP mediante endpoints REST.

exception: Contiene excepciones personalizadas para manejo de errores.

model: Define entidades JPA que representan tablas de la base de datos.

repository: Interfaces y clases que interactúan con la base de datos.

service: Implementa la lógica de negocio.

UsuariosApplication.java: Clase principal que inicia la aplicación.

📂 src/main/resources

application.properties: Archivo de configuración para la aplicación (base de datos, puerto, etc.).

🔧 Configuración de la base de datos

Base de datos: clientes

Tabla: usuarios

CREATE TABLE usuarios(
    id bigint NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nombre varchar(100) DEFAULT NULL,
    apellido varchar(100) DEFAULT NULL,
    email varchar(100) DEFAULT NULL
);

📌 Configuración (application.properties)

spring.application.name=usuarios
spring.datasource.username=root
spring.datasource.password=277353
spring.datasource.url=jdbc:mysql://localhost:3306/clientes
server.servlet.context-path=/users
