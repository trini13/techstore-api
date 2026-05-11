# TechStore API

Microservicio desarrollado con Java y Spring Boot para la gestión de productos de la tienda TechStore Chile.

## Tecnologías utilizadas

- Java 17
- Spring Boot
- Spring Data JPA
- Spring Security
- PostgreSQL
- Maven
- Docker
- Git y GitHub
- Postman

## Funcionalidades

- Listar productos
- Crear productos
- Modificar productos
- Eliminar productos de forma lógica (activo = false)
- Persistencia en base de datos PostgreSQL
- Empaquetado en archivo .jar

## Endpoints principales

- `GET /api/productos`
- `POST /api/productos`
- `PUT /api/productos/{id}`
- `DELETE /api/productos/{id}`

## Configuración de base de datos

El proyecto utiliza PostgreSQL en Docker.

Comando para levantar la base de datos:

```bash
docker run --name techstoredb -e POSTGRES_DB=techstore -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin123 -p 5432:5432 -d postgres:15
```

## Configuración en application.properties

```properties
spring.application.name=techstore-api

spring.datasource.url=jdbc:postgresql://localhost:5432/techstore
spring.datasource.username=admin
spring.datasource.password=admin123
spring.datasource.driver-class-name=org.postgresql.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

## Cómo ejecutar el proyecto

1. Clonar el repositorio:

```bash
git clone https://github.com/trini13/techstore-api.git
```

2. Entrar a la carpeta del proyecto:

```bash
cd techstore-api
```

3. Levantar PostgreSQL con Docker:

```bash
docker run --name techstoredb -e POSTGRES_DB=techstore -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin123 -p 5432:5432 -d postgres:15
```

4. Ejecutar la aplicación desde IntelliJ o desde terminal con Maven Wrapper:

```bash
./mvnw clean spring-boot:run
```

En Windows PowerShell:

```powershell
.\mvnw.cmd clean spring-boot:run
```

5. Generar el archivo .jar:

```powershell
.\mvnw.cmd clean package -DskipTests
```

6. Ejecutar el .jar:

```powershell
java -jar target\techstore-api-0.0.1-SNAPSHOT.jar
```

## Pruebas con Postman

Ejemplo de JSON para crear un producto:

```json
{
  "nombre": "Laptop Lenovo IdeaPad",
  "descripcion": "Notebook 15.6 pulgadas, 8GB RAM, 512GB SSD",
  "precio": 499990,
  "stock": 15,
  "categoria": "Computacion",
  "activo": true
}
```

## Autores

- Cristina Trinidad Silva Huenchullan