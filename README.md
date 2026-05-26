<div align="center">

<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" />
<img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white" />
<img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white" />

<br/><br/>

# Nexus Employee Portal

### *Full-Stack Employee Management System*

> **Nexus** is a production-grade employee management web application built with **Java OOP**, **Spring Boot**, and **Thymeleaf** — demonstrating a clean MVC architecture with full CRUD operations, server-side rendering, and client-side validation.

<br/>

[Features](#-features) • [Tech Stack](#-tech-stack) • [Architecture](#-architecture) • [Getting Started](#-getting-started)

</div>

---

## The Problem

Managing employee records across an organization requires a reliable, structured system. Spreadsheets break down at scale — data gets duplicated, records go missing, and there's no validation or access control. A dedicated portal solves all of this.

## The Solution

**Nexus Employee Portal** is a full-stack web application that gives organizations a clean, structured way to manage their workforce. Built on Spring Boot's proven architecture with Thymeleaf for seamless server-side rendering, Nexus demonstrates how modern Java web development works end to end — from HTTP request to database and back.

---

## Features

### Employee CRUD Operations
Complete lifecycle management for employee records.

- **Create** — Add new employees with full form validation
- **Read** — View the complete employee list with search and filter
- **Update** — Edit employee details with pre-populated forms
- **Delete** — Remove records with confirmation flow
- Efficient data management using **Spring Data JPA** and **Java Collections**

### Java OOP Architecture
Enterprise-grade code structure applying core OOP principles throughout.

- **Encapsulation** — Employee model with private fields and getters/setters
- **Abstraction** — Service layer abstracts business logic from controllers
- **Inheritance** — Shared base classes for common entity behaviour
- **Polymorphism** — Flexible service interfaces with concrete implementations

### Spring Boot Backend
Modular, maintainable architecture following the MVC pattern.

- **Controllers** — Handle HTTP requests and route to appropriate views
- **Services** — Encapsulate business logic cleanly away from the data layer
- **Repositories** — Spring Data JPA handles all database interaction
- Embedded **Tomcat** server — no external server configuration needed
- **Maven** build tool for dependency management and project lifecycle

### Thymeleaf Frontend
Dynamic, server-rendered web pages with full interactivity.

- **Dynamic content rendering** — Employee data bound directly from the model
- **Conditional rendering** — UI adapts based on employee status and role
- **Loops** — Efficient iteration over employee collections in templates
- **Data binding** — Two-way binding between forms and Java model objects
- **Client-side validation** — JavaScript validation before form submission
- **Responsive UI** — Clean, easy-to-navigate interface for all screen sizes

---

## Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Language** | Java | Core application logic and OOP principles |
| **Framework** | Spring Boot | Application framework, dependency injection, auto-configuration |
| **ORM** | Spring Data JPA | Database abstraction and repository pattern |
| **Template Engine** | Thymeleaf | Server-side HTML rendering with dynamic data binding |
| **Frontend** | HTML · CSS · JavaScript | UI structure, styling, and client-side validation |
| **Database** | MySQL / H2 | Persistent employee data storage |
| **Build Tool** | Maven | Dependency management and build lifecycle |
| **Server** | Embedded Tomcat | HTTP server bundled with Spring Boot |

---

## Architecture

```
┌──────────────────────────────────────────────────────┐
│                   Browser (Client)                    │
│              Thymeleaf rendered HTML                 │
│          HTML · CSS · JavaScript validation          │
└────────────────────────┬─────────────────────────────┘
                         │ HTTP Request
                         ▼
┌──────────────────────────────────────────────────────┐
│              Spring Boot Application                  │
│                                                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │
│  │ Controller  │→ │   Service   │→ │ Repository  │  │
│  │  layer      │  │   layer     │  │   layer     │  │
│  │ HTTP routes │  │  Business   │  │ Spring Data │  │
│  │ Model setup │  │  logic      │  │ JPA queries │  │
│  └─────────────┘  └─────────────┘  └──────┬──────┘  │
└──────────────────────────────────────────┼───────────┘
                                           │
                                           ▼
                         ┌─────────────────────────────┐
                         │        MySQL / H2            │
                         │    Employee records DB       │
                         └─────────────────────────────┘
```

### MVC Flow

```
HTTP GET /employees
        ↓
EmployeeController.listEmployees()
        ↓
EmployeeService.getAllEmployees()
        ↓
EmployeeRepository.findAll()  ← Spring Data JPA
        ↓
List<Employee> returned
        ↓
Thymeleaf renders employees/list.html
        ↓
HTML response sent to browser
```

---

## Project Structure

```
Nexus-Employee-Portal/
├── employees/
│   └── src/main/
│       ├── java/com/nexus/employees/
│       │   ├── controller/
│       │   │   └── EmployeeController.java    # HTTP routes and model setup
│       │   ├── model/
│       │   │   └── Employee.java              # Entity class with OOP principles
│       │   ├── repository/
│       │   │   └── EmployeeRepository.java    # Spring Data JPA interface
│       │   ├── service/
│       │   │   ├── EmployeeService.java        # Service interface
│       │   │   └── EmployeeServiceImpl.java    # Business logic implementation
│       │   └── NexusApplication.java          # Spring Boot entry point
│       └── resources/
│           ├── templates/
│           │   ├── employees/
│           │   │   ├── list.html              # Employee list view
│           │   │   ├── add.html               # Add employee form
│           │   │   └── edit.html              # Edit employee form
│           │   └── layout/
│           │       └── base.html              # Base Thymeleaf layout
│           └── application.properties         # DB and server config
├── frontend/                                  # Static assets
└── pom.xml                                    # Maven dependencies
```

---

## Getting Started

### Prerequisites

- Java `>=17`
- Maven `>=3.6`
- MySQL (or use the built-in H2 for quick start)
- IntelliJ IDEA or any Java IDE

### Installation

```bash
# Clone the repository
git clone https://github.com/chamethyaY/Nexus-Employee-Portal.git
cd Nexus-Employee-Portal
```

### Database Setup (MySQL)

```sql
CREATE DATABASE nexus_db;
```

Update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/nexus_db
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### Quick Start with H2 (no MySQL needed)

```properties
spring.datasource.url=jdbc:h2:mem:nexusdb
spring.datasource.driver-class-name=org.h2.Driver
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
```

### Run the Application

```bash
# Build the project
mvn clean install

# Run with Maven
mvn spring-boot:run
```

Open your browser and go to: **http://localhost:8080/employees**

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/employees` | List all employees |
| `GET` | `/employees/add` | Show add employee form |
| `POST` | `/employees/save` | Create or update employee |
| `GET` | `/employees/edit/{id}` | Show edit form for employee |
| `GET` | `/employees/delete/{id}` | Delete employee by ID |

---

## Key Implementation Highlights

### Spring Data JPA Repository
```java
public interface EmployeeRepository extends JpaRepository<Employee, Long> {
    List<Employee> findByDepartment(String department);
    List<Employee> findByLastNameContainingIgnoreCase(String name);
}
```

### Service Layer Pattern
```java
@Service
public class EmployeeServiceImpl implements EmployeeService {

    @Autowired
    private EmployeeRepository employeeRepository;

    @Override
    public List<Employee> getAllEmployees() {
        return employeeRepository.findAll();
    }

    @Override
    public void saveEmployee(Employee employee) {
        employeeRepository.save(employee);
    }

    @Override
    public void deleteEmployee(Long id) {
        employeeRepository.deleteById(id);
    }
}
```

### Thymeleaf Data Binding
```html
<!-- Employee list with Thymeleaf iteration -->
<tr th:each="employee : ${employees}">
    <td th:text="${employee.firstName}"></td>
    <td th:text="${employee.lastName}"></td>
    <td th:text="${employee.email}"></td>
    <td th:text="${employee.department}"></td>
    <td>
        <a th:href="@{/employees/edit/{id}(id=${employee.id})}">Edit</a>
        <a th:href="@{/employees/delete/{id}(id=${employee.id})}">Delete</a>
    </td>
</tr>
```

---

## What I Learned

Building Nexus reinforced key enterprise Java concepts:

- **MVC separation of concerns** — keeping controllers thin, services rich
- **Spring Boot auto-configuration** — understanding convention over configuration
- **JPA entity relationships** — mapping Java objects to database tables
- **Thymeleaf template inheritance** — building reusable layout components
- **Form validation** — combining server-side (Spring) and client-side (JavaScript) validation
- **Maven dependency management** — managing a multi-layer Java project

---

## Author

**Chamethya Yasodie**
Full-Stack Developer · BSc Computer Science · University of Westminster (IIT Colombo)

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">
  <sub>Built with Java by Chamethya Yasodie</sub>
</div>
