This repository contains a Spring Boot REST API application designed to manage student records. It utilizes Spring Data JPA for database interactions and exposes a set of RESTful endpoints for CRUD (Create, Read, Update, Delete) operations.


# Spring Boot REST API Application

This is a Spring Boot application that provides a RESTful web service for managing student information. It is built using the Spring Boot framework, Spring Data JPA, and a MySQL database.

## Project Structure

The project follows a standard Spring Boot layered architecture:
* **Entity**: Contains the `Student` model which represents the database table.
* **Repository**: Contains the `StudentRepository` interface for database operations using Spring Data JPA.
* **Service**: Defines the business logic through the `StudentService` interface and its implementation `StudentServiceImpl`.
* **Controller**: Handles incoming REST API requests and maps them to service methods.

## Prerequisites

* Java 17
* Maven 3.x
* MySQL Database

## Configuration

The database connection details are located in `src/main/resources/application.properties`. You should update the following properties with your local MySQL credentials:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/student_rest_api
spring.datasource.username=root
spring.datasource.password=your_password
```

By default, the application is configured to automatically update the database schema (`hibernate.ddl-auto=update`) based on the `Student` entity.

## REST API Endpoints

The application provides the following endpoints under the base path `/api/`:

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **POST** | `/api/saveStudent` | Create a new student record. |
| **GET** | `/api/getAllStudent` | Retrieve a list of all students. |
| **PUT** | `/api/editStudent/{id}` | Update an existing student's details by ID. |
| **DELETE** | `/api/deleteStudent/{id}` | Delete a student record by ID. |

## Running the Application

You can run the application using the included Maven Wrapper:

### On Windows:
```bash
./mvnw.cmd spring-boot:run
```

### On Linux/macOS:
```bash
./mvnw spring-boot:run
```

The application will start, and the REST API will be accessible at `http://localhost:8080`.

## Testing

Basic context loading tests are included in the `src/test/` directory. You can run them using:
```bash
./mvnw test
```
