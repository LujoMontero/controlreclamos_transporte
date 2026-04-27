<div align="center">

# 🚌 Control de Reclamos — Transporte Público

### Spring Boot · Thymeleaf · MySQL · Maven · MVC

![Java](https://img.shields.io/badge/Java_17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)

</div>

---

## 📌 ¿Qué hace este proyecto?

Aplicación web **MVC** para la gestión de reclamos de usuarios del transporte público. Permite registrar, consultar y hacer seguimiento al estado de reclamos (retraso, trato del conductor, condición del vehículo, etc.), con interfaz web construida con Thymeleaf y persistencia en MySQL.

---

## 🏗️ Arquitectura MVC

```
Navegador
    │
    ▼
[Thymeleaf View]          ← HTML renderizado server-side
    │
    ▼
[Spring Controller]       ← Recibe requests, delega a servicio
    │
    ▼
[Service Layer]           ← Lógica de negocio y validaciones
    │
    ▼
[Repository - JPA]        ← Acceso a datos con Hibernate
    │
    ▼
[MySQL Database]          ← Persistencia de reclamos y usuarios
```

---

## ✨ Funcionalidades

- **Registro de reclamos**: formulario con tipo, descripción, línea de bus y fecha
- **Listado de reclamos**: vista con todos los reclamos registrados
- **Estado de seguimiento**: pendiente, en proceso, resuelto
- **Validaciones**: campos obligatorios, formatos de datos y longitudes
- **Interfaz responsiva**: vistas Thymeleaf adaptadas a distintos tamaños

---

## 🗂️ Estructura del proyecto

```
controlreclamos_transporte/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/reclamos/
│   │   │       ├── controller/   # Controladores Spring MVC
│   │   │       ├── model/        # Entidades JPA
│   │   │       ├── repository/   # Repositorios Spring Data
│   │   │       └── service/      # Lógica de negocio
│   │   └── resources/
│   │       ├── templates/        # Vistas Thymeleaf (.html)
│   │       └── application.properties
│   └── test/
│       └── java/                 # Pruebas unitarias
└── pom.xml
```

---

## ⚙️ Requisitos

- Java 17+
- Maven 3.8+
- MySQL 8+

---

## 🚀 Instalación y ejecución

```bash
# 1. Clonar el repositorio
git clone https://github.com/LujoMontero/controlreclamos_transporte.git
cd controlreclamos_transporte

# 2. Crear la base de datos en MySQL
mysql -u root -p
CREATE DATABASE control_reclamos;
EXIT;

# 3. Configurar conexión en application.properties
# src/main/resources/application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/control_reclamos
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
spring.jpa.hibernate.ddl-auto=update

# 4. Compilar y ejecutar
mvn spring-boot:run

# 5. Abrir en el navegador
open http://localhost:8080
```

---

## 🗄️ Modelo de datos

```
Reclamo
├── id (PK)
├── tipo          → RETRASO | CONDUCTOR | VEHICULO | OTRO
├── descripcion
├── lineaBus
├── fecha
├── estado        → PENDIENTE | EN_PROCESO | RESUELTO
└── usuario_id (FK)

Usuario
├── id (PK)
├── nombre
├── email
└── telefono
```

---

## 🧪 Ejecutar pruebas

```bash
mvn test
```

---

## 💡 Conceptos aplicados

- **Spring MVC**: separación clara entre capa de presentación, negocio y datos
- **Thymeleaf**: motor de plantillas server-side integrado con Spring
- **Spring Data JPA + Hibernate**: abstracción de acceso a base de datos relacional
- **Validaciones con Bean Validation**: anotaciones `@NotNull`, `@Size`, etc.

---

## 👨‍💻 Autor

**Luis Montero** · [GitHub](https://github.com/LujoMontero) · [LinkedIn](https://www.linkedin.com/in/luis-montero-if/)
