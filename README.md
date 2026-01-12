# SEU Library Management System

A comprehensive web-based library management system built with Spring Boot that enables efficient management of books, members, and borrowing operations.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Default Credentials](#default-credentials)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Contributing](#contributing)

## 🎯 Overview

The SEU Library Management System is a full-stack web application designed to streamline library operations. It provides separate interfaces for administrators and members, enabling book management, member registration, book lending, and tracking of borrowed books.

## ✨ Features

### Admin Features
- **Member Management**
  - Add new members with unique IDs
  - View all registered members
  - Search members by name
  - Edit member information
  - Delete members from the system

- **Book Management**
  - Add new books with ISBN, author, and copy information
  - Track total and available copies
  - View all books in the library
  - Automatic availability updates

- **Lending Operations**
  - Lend books to registered members
  - Set return dates for borrowed books
  - View all borrowed books
  - Track borrowing history
  - Process book returns
  - Prevent duplicate borrowing (same book by same member)

### Member Features
- Secure member login
- View personal borrowing history
- Browse available books

## 🛠 Technology Stack

- **Backend Framework:** Spring Boot 3.4.5
- **Language:** Java 24
- **Database:** MySQL
- **ORM:** Spring Data JPA with Hibernate
- **Template Engine:** Thymeleaf
- **Build Tool:** Maven
- **Development Tools:** Spring Boot DevTools

### Dependencies
- Spring Boot Starter Web
- Spring Boot Starter Data JPA
- Spring Boot Starter Thymeleaf
- MySQL Connector
- Spring Boot DevTools

## 📦 Prerequisites

Before you begin, ensure you have the following installed:
- Java Development Kit (JDK) 24 or higher
- Apache Maven 3.6+
- MySQL Server 5.7+ or 8.0+
- Git (for version control)
- An IDE (IntelliJ IDEA, Eclipse, or VS Code recommended)

## 🚀 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/dewannadim007-create/java_project_library.git
cd java_project_library/seulibrary
```

### 2. Set Up MySQL Database
Create a new database for the application:
```sql
CREATE DATABASE seuproject;
```

### 3. Configure Database Connection
Edit `src/main/resources/application.properties` with your MySQL credentials:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/seuproject
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD
```

### 4. Build the Project
```bash
mvn clean install
```

## ⚙️ Configuration

The application configuration is located in `src/main/resources/application.properties`:

```properties
# Application Name
spring.application.name=seulibrary

# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/seuproject
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

# JPA/Hibernate Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

# Server Configuration
server.port=7777
```

**Important:** Change the default database password before deploying to production.

## 🏃 Running the Application

### Using Maven
```bash
mvn spring-boot:run
```

### Using Java
```bash
java -jar target/seulibrary-0.0.1-SNAPSHOT.jar
```

### Using Maven Wrapper (Unix/Linux/macOS)
```bash
./mvnw spring-boot:run
```

### Using Maven Wrapper (Windows)
```cmd
mvnw.cmd spring-boot:run
```

Once started, the application will be available at:
```
http://localhost:7777
```

## 🔐 Default Credentials

### Admin Access
- **User ID:** 111
- **Password:** 123

**Note:** It is highly recommended to change these default credentials after the first login for security purposes.

## 📁 Project Structure

```
seulibrary/
├── src/
│   ├── main/
│   │   ├── java/bd/edu/seu/seulibrary/
│   │   │   ├── controller/          # Web controllers
│   │   │   │   ├── AdminController.java
│   │   │   │   ├── AuthController.java
│   │   │   │   └── MemberController.java
│   │   │   ├── model/              # Entity classes
│   │   │   │   ├── Admin.java
│   │   │   │   ├── Book.java
│   │   │   │   ├── BorrowedBook.java
│   │   │   │   └── Member.java
│   │   │   ├── repository/         # Data access layer
│   │   │   │   ├── AdminRepository.java
│   │   │   │   ├── BookRepository.java
│   │   │   │   ├── BorrowedBookRepository.java
│   │   │   │   └── MemberRepository.java
│   │   │   ├── services/          # Business logic
│   │   │   │   ├── AdminService.java
│   │   │   │   ├── BookService.java
│   │   │   │   ├── BorrowedBookService.java
│   │   │   │   └── MemberService.java
│   │   │   └── SeulibraryApplication.java
│   │   └── resources/
│   │       ├── static/            # Static resources (CSS, JS, images)
│   │       ├── templates/         # Thymeleaf templates
│   │       └── application.properties
│   └── test/                      # Test classes
├── mvnw                           # Maven wrapper script (Unix)
├── mvnw.cmd                       # Maven wrapper script (Windows)
└── pom.xml                        # Maven configuration
```

## 📖 Usage

### For Administrators

1. **Access the Application**
   - Navigate to `http://localhost:7777`
   - Login with admin credentials

2. **Managing Members**
   - Add new members through the "Add Member" page
   - View all members in the member list
   - Search for specific members by name
   - Edit or delete existing members

3. **Managing Books**
   - Add new books with complete details (title, ISBN, author, copies)
   - Click the refresh button on the admin home page to see available books
   - The system automatically tracks available copies

4. **Lending Books**
   - Select a book and member from the lend book page
   - Set a return date
   - The system prevents duplicate lending of the same book to the same member

5. **Tracking Borrowed Books**
   - View all borrowed books in the borrowed books list
   - Mark books as returned
   - Delete borrowing records when needed

### For Members

1. **Login**
   - Use your member ID and password provided by the admin

2. **View Books**
   - Browse available books in the library

3. **Check Borrowing History**
   - View your current and past borrowed books

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature-name`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature-name`)
5. Open a Pull Request

## 📄 License

This project is available for educational purposes.

## 👥 Authors

- Southeast University Team

## 📞 Support

For issues or questions, please open an issue on the GitHub repository.

---

**Note:** This is an educational project. Ensure proper security measures are implemented before deploying to a production environment.
