# 📝 To-Do Application (Spring Boot + MySQL)

A simple and production-ready **To-Do List App** built with **Spring Boot**, **MySQL**, and **REST APIs**.

---

## 🚀 Features

* Add new tasks
* View all tasks
* Update tasks
* Mark tasks as completed
* Delete tasks
* Persistent storage using **MySQL database**
* Clean, modular Spring Boot architecture
* Supports deployment on cloud / VPS
---

## 🛠️ Tech Stack

* **Java 17/21**
* **Spring Boot 3.x**
* **Spring Web**
* **Spring Data JPA**
* **MySQL Database**
* **Lombok**
* **Maven**

---

## 📁 Project Structure

```
src/main/java/com/example/todo
│
├── controller
│     └── TaskController.java
├── service
│     └── TaskService.java
├── repository
│     └── TaskRepository.java
└── entity
      └── Task.java

src/main/resources
└── application.properties
```

---

## ⚙️ Setup Instructions

### 1️⃣ Install MySQL and create a database

```sql
CREATE DATABASE todo_app;
```

---

### 2️⃣ Add MySQL configuration in `application.properties`

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/todo_app?useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=your_mysql_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect
```

---

### 3️⃣ Run the application

```bash
mvn spring-boot:run
```

Server runs at:
➡️ **[http://localhost:8080](http://localhost:8080)**

---

## 🧪 API Endpoints

### ➕ Create Task

`POST /api/tasks`

```json
{
  "title": "Learn Spring Boot",
  "description": "Complete CRUD implementation"
}
```

---

### 📄 Get All Tasks

`GET /api/tasks`

---

### 🔍 Get Task by ID

`GET /api/tasks/{id}`

---

### ✏️ Update Task

`PUT /api/tasks/{id}`

```json
{
  "title": "Learn Spring Boot (Updated)",
  "description": "Improve service layer",
  "completed": false
}
```

---

### ✔️ Mark as Completed

`PATCH /api/tasks/{id}/complete`

---

### ❌ Delete Task

`DELETE /api/tasks/{id}`

---

## 📦 Entity Example

```java
@Entity
@Data
public class Task {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @NotBlank
    private String title;

    private String description;

    private boolean completed = false;
}
```

---

## 🔧 MySQL Table Auto-Generation

Because `spring.jpa.hibernate.ddl-auto=update`, Spring Boot will automatically create the `task` table in MySQL.

---

## 🧰 Build & Run

### Build JAR

```bash
mvn clean install
```

### Run JAR

```bash
java -jar target/todo-app-0.0.1-SNAPSHOT.jar
```

---

## 📜 License

Open-source — MIT License.

---

## 🙋 Author

**Your Name**
GitHub: [https://github.com/your-username](https://github.com/TusharikaSh27)
