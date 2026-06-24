To create this file on GitHub, go to your repository, click Add file > Create
new file, name it README.md, and paste the following content:

# Library Management System (Spring XML Configuration)

This is a basic Java application developed to demonstrate the core concepts of the **Spring Framework**, specifically **Inversion of Control (IoC)** and **Dependency Injection (DI)** using XML-based configuration.

## 📖 Scenario
A library needs a backend system to manage books. We use Spring to handle the creation of the Service and Repository layers and to manage the relationship between them without manually instantiating objects.

## 🛠 Tech Stack
*   **Java**: 11 or higher
*   **Framework**: Spring Core (Context)
*   **Build Tool**: Maven
*   **IDE**: VS Code (on macOS)

## 📂 Project Structure
```text
LibraryManagement/
├── pom.xml
└── src/
    └── main/
        ├── java/
        │   └── com/library/
        │       ├── App.java
        │       ├── repository/
        │       │   └── BookRepository.java
        │       └── service/
        │           └── BookService.java
        └── resources/
            └── applicationContext.xml

⚙️ Configuration Files

1. Maven Dependencies (pom.xml)

The project uses the spring-context library to enable Spring's core features.

<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>5.3.29</version>
</dependency>

2. Spring XML Config (applicationContext.xml)

This file defines the beans and their dependencies.

<bean id="bookRepository" class="com.library.repository.BookRepository" />

<bean id="bookService" class="com.library.service.BookService">
    <property name="bookRepository" ref="bookRepository" />
</bean>

🚀 How to Run (macOS)

1.  Clone the project or open the folder in VS Code.
2.  Open the Terminal in the project root directory.
3.  Compile the code:
    mvn clean compile
4.  Run the application:
    mvn exec:java -Dexec.mainClass="com.library.App"

📊 Expected Result

After running, you should see the following output in the terminal:

Service layer: Listing books...
Fetching all books from the database...

💡 Key Lessons

  - IoC Container: We learned how to use ClassPathXmlApplicationContext to start
    the Spring container.
  - Dependency Injection: Instead of using the new keyword, Spring "injected"
    the BookRepository into the BookService using Setter Injection.
  - Decoupling: The service layer doesn't need to know how to create the
    repository, making the code more maintainable.

Created for Spring Framework Training.

