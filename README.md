# Proyecto CRUD de Gestión de Libros

Este proyecto es una aplicación de escritorio que permite la gestión de un conjunto de libros utilizando Java Swing para la interfaz gráfica de usuario (GUI) y una base de datos MySQL para almacenar la información. Se implementa un CRUD completo (Crear, Leer, Actualizar y Eliminar) para los libros, interactuando con la base de datos a través de un patrón DAO (Data Access Object).

## Características

- **Interfaz gráfica**: La aplicación tiene una interfaz gráfica sencilla e intuitiva creada con Java Swing.
- **CRUD**: Permite crear, listar, actualizar y eliminar libros.
- **Conexión a base de datos**: Utiliza MySQL como sistema de base de datos para almacenar la información de los libros.
- **Modelo DAO**: La arquitectura utiliza el patrón DAO para gestionar la interacción con la base de datos, separando la lógica de negocio de la capa de presentación.

## Estructura del Proyecto

El proyecto está dividido en tres partes principales:

1. **Modelo (`Book`)**: Representa la estructura de un libro, incluyendo su ID, título, autor y año de publicación.
2. **DAO (`BookDAO`)**: Se encarga de interactuar con la base de datos, realizando operaciones como insertar, seleccionar, actualizar y eliminar libros.
3. **Vista (`BookView`)**: Interfaz gráfica que permite al usuario interactuar con el sistema de libros. Proporciona campos de entrada para ingresar datos y botones para realizar las operaciones CRUD.

### Clases principales

#### 1. `Book.java`
Esta clase representa el modelo de un libro. Contiene los atributos de un libro, como el ID, el título, el autor y el año de publicación, junto con los métodos getter y setter.

#### 2. `BookDAO.java`
La clase `BookDAO` es responsable de las operaciones con la base de datos. Incluye métodos para:
- Insertar un nuevo libro (`insertBook`).
- Recuperar todos los libros (`getBooks`).
- Actualizar el título de un libro (`updateBook`).
- Eliminar un libro por su ID (`deleteBook`).

#### 3. `BookView.java`
Esta clase es la interfaz gráfica construida con Swing. Ofrece las siguientes funcionalidades:
- **Agregar libro**: Ingresar un título, autor y año para añadir un libro a la base de datos.
- **Listar libros**: Mostrar una tabla con todos los libros disponibles.
- **Actualizar libro**: Actualizar el título de un libro existente.
- **Eliminar libro**: Eliminar un libro especificando su ID.

## Requisitos del sistema

### Software
- **Java 8 o superior**: Asegúrate de tener una versión de Java compatible.
- **MySQL**: Debes tener un servidor MySQL en funcionamiento.
- **JDBC MySQL Connector**: Para conectar la aplicación Java con la base de datos MySQL.

### Dependencias de la base de datos
Crea una base de datos MySQL llamada `libros_db` con la siguiente tabla:

```sql
CREATE DATABASE libros_db;

USE libros_db;

CREATE TABLE books (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100),
    author VARCHAR(100),
    year INT
);
