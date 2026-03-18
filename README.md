## Employee Management System

Full-Stack Java Web Application using Spring Boot & Thymeleaf
Year: 2025

 ##Overview

The Employee Management System is a web application designed to help organizations manage employee data efficiently. It enables users to create, read, update, and delete employee records while showcasing Java OOP principles, modular backend design, and interactive front-end features.

This project demonstrates best practices in full-stack development, integrating Spring Boot, Thymeleaf, Spring Data JPA, and Java Collections.

##Key Features

##CRUD Operations

Add, view, edit, and delete employee records

Efficient data management using Spring Data JPA and Java Collections

Modular Backend

Built with Spring Boot controllers and services

Follows Java OOP principles: encapsulation, inheritance, and polymorphism

Interactive Frontend

Dynamic pages built with Thymeleaf templates

Conditional rendering, loops, and data binding

Client-side validation using JavaScript

Employee Data Management

Forms directly bound to backend models

Real-time updates to employee information

🛠 Technologies Used
Layer	Technology / Tools
Backend	Java 17+, Spring Boot, Spring Data JPA
Frontend	Thymeleaf, HTML5, CSS3, JavaScript
Database	H2 (In-memory) / Optional: MySQL
Build Tools	Maven
🗂 Project Structure
employee-management-system/
│
├─ src/main/java/com/example/ems/
│   ├─ controller/       # Spring Boot controllers
│   ├─ service/          # Business logic layer
│   ├─ model/            # Employee entity & models
│   └─ repository/       # Spring Data JPA repositories
│
├─ src/main/resources/templates/  # Thymeleaf HTML templates
├─ src/main/resources/static/     # CSS, JavaScript, images
└─ src/main/resources/application.properties  # Spring Boot config
🖼 Screenshots

You can add screenshots of the application pages here, e.g.:

Employee List Page

Add Employee Form

Update Employee Details

⚙️ How to Run

Clone the repository

git clone https://github.com/your-username/employee-management-system.git
cd employee-management-system

Build the project

mvn clean install

Run the Spring Boot application

mvn spring-boot:run

Open the application in your browser

http://localhost:8080
🔮 Future Improvements

Add user authentication & authorization for admin and employees

Integrate with MySQL or PostgreSQL for production use

Add reporting & analytics features (attendance, performance)

Expose REST API endpoints for mobile app integration

👤 Author

Chamethya Yasodie
Computer Science Student | Aspiring Software Developer
