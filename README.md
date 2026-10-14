MapFinance – Online Personal Finance Management Platform
1. Project Overview
MapFinance is a Java web-based personal finance management platform. It helps users manage their finances by recording income and expenses, creating budgets, tracking financial goals, and reviewing financial reports. The application also provides an administrator area for managing user accounts and administrative operations.
The project combines a React frontend with a Java Spring Boot backend and a MySQL database.
2. Problem Statement
Managing personal finances manually can make it difficult to understand spending habits, maintain budgets, and track savings goals. MapFinance provides a centralized application for organizing financial records and monitoring personal financial activities.
3. Project Objectives
- Record and manage income and expenses.
- Organize transactions by category.
- Create and monitor budgets.
- Set and track financial goals.
- Review financial summaries and reports.
- Provide authentication and role-based access.
- Design a clear and responsive user interface.
- Integrate the frontend, backend, and database.
4. Main Features
User Features
- User registration and login.
- Financial dashboard.
- Income and expense transaction management.
- Budget creation and monitoring.
- Financial goal management.
- Financial reports.
- Profile management.
Admin Features
- Administrative dashboard.
- User account management.
- Access to administrative functions according to permissions.
5. Technology Stack
Area	Technology
Frontend	React.js, Vite, CSS
Backend	Java, Spring Boot
Build tool	Maven
API communication	REST APIs
Security	Spring Security, JWT
Database	MySQL
Database hosting	Aiven MySQL
Frontend hosting	Vercel
Backend hosting	Render
Version control	Git and GitHub


6. System Architecture
The application uses a client-server architecture. The React frontend sends HTTP requests to REST API endpoints exposed by the Spring Boot backend. The backend handles application logic, authentication, authorization, and database operations. MySQL stores the application data.
                 User / Admin
                      |
                      v
             React + Vite Frontend
                      |
                 HTTP / REST
                      |
                      v
             Java Spring Boot API
                      |
          +-----------+-----------+
          |           |           |
          v           v           v
     Controllers   Security   Application
                   (JWT)        Logic
                      |
                      v
                Database Access
                      |
                      v
                 MySQL (Aiven)
7. Project Structure
Java-Project/
├── backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       └── resources/
│   ├── .env.example
│   ├── Dockerfile
│   └── pom.xml
├── frontend/
│   ├── public/
│   ├── src/
│   ├── .env.example
│   ├── package.json
│   ├── package-lock.json
│   └── vite.config.js
├── .gitignore
└── README.md
This is a high-level overview of the repository. Refer to the source folders for the complete implementation.
8. Database Design and Connectivity
MapFinance uses a relational MySQL database hosted on Aiven. The application's data model supports the main areas of the platform, including user accounts, transaction categories, transactions, budgets, and financial goals.
The Spring Boot backend connects to MySQL using the configured database connection and MySQL JDBC driver. Database settings are provided through application configuration and environment variables. SQL initialization files may be used where configured by the application.
Logical entities
- User: Account and authentication-related information.
- Category: Categories used to organize financial records.
- Transaction: Income and expense records.
- Budget: Budget limits and associated categories.
- Goal: Financial targets and progress.
The actual table names, columns, and relationships are defined by the database schema implemented in the project.
9. User Interface and Responsiveness
The frontend is developed with React and Vite. The interface is organized into reusable components and pages for the dashboard, transactions, budgets, goals, reports, profile, and administration.
The design aims to provide:
- Consistent styling across user and admin pages.
- Clear navigation and readable layouts.
- Forms for entering and managing financial data.
- Dashboard summaries for important financial information.
- Responsive layouts for supported desktop and mobile screen sizes.
10. Requirements
Before running the project, prepare:
- A Java JDK version compatible with the backend configuration.
- Maven, or the Maven Wrapper if included in the repository.
- Node.js and npm.
- Access to a MySQL database.
- Git.
- A code editor such as Visual Studio Code.
11. Setup and Running Instructions
Step 1: Clone the repository
git clone https://github.com/ankit-1010/Java-Project.git
cd Java-Project
Step 2: Configure the backend
Open the backend directory. Use backend/.env.example as a reference for the required configuration variables.
Set the database connection details, JWT secret, and any other required settings using the configuration method supported by the application. Make sure the MySQL database is available and that the credentials are valid.
Run the backend from the backend directory:
mvn spring-boot:run
If a Maven Wrapper is included, it can be used instead of a separately installed Maven executable.
Step 3: Configure the frontend
Open a separate terminal in the project root and run:
cd frontend
npm install
Use frontend/.env.example to identify the frontend environment variables. Configure the API base URL to point to the backend instance you intend to use.
Start the frontend development server:
npm run dev
Open the local URL printed in the terminal by Vite. Features that use the API require both the frontend and backend to be running and configured correctly.
12. Deployment
The project uses the following deployment services:
- Frontend: Vercel
- Backend: Render
- Database: Aiven MySQL
For deployment, configure the frontend with the correct backend API URL. Configure the backend hosting environment with the required database settings, JWT secret, and CORS allowed origins.
13. Code Quality and Security
The project separates the frontend and backend to keep the code organized. React components and backend modules help separate responsibilities and support maintainability.
Security-related configuration should be stored in environment variables or the hosting provider's secret settings. Do not commit real .env files, database passwords, JWT secrets, or administrator credentials to GitHub.
14. Conclusion
MapFinance is a full-stack personal finance management application that brings together frontend development, Java backend development, database connectivity, security, and deployment. It is designed to help users organize transactions, manage budgets, and monitor financial goals while demonstrating core concepts in web application development.
