# MapFinance – Online Personal Finance Management Platform


##Website URL - https://java-project-frontend-amber.vercel.app/

## 1. Project Overview

**MapFinance** is a Java web-based personal finance management platform that helps users manage their finances by recording income and expenses, creating budgets, tracking financial goals, and reviewing financial reports. The application also provides an administrator module for managing user accounts and administrative operations.

The project combines a React frontend, a Java Spring Boot backend, and a MySQL database.

## 2. Problem Statement

Managing personal finances manually can make it difficult to understand spending habits, maintain budgets, and track savings goals. MapFinance provides a centralized platform for organizing financial records and monitoring personal financial activities.

## 3. Project Objectives

- Record and manage income and expenses.
- Organize transactions by category.
- Create and monitor budgets.
- Set and track financial goals.
- Review financial summaries and reports.
- Provide authentication and role-based access.
- Design a clear and responsive user interface.
- Integrate the frontend, backend, and database.

## 4. Main Features

### User Module

- User registration and login.
- Financial dashboard.
- Income and expense transaction management.
- Budget creation and monitoring.
- Financial goal management.
- Financial reports.
- Profile management.

### Admin Module

- Administrative dashboard.
- User account management.
- Access to administrative functions according to permissions.

## 5. Technology Stack

| Component | Technology |
|---|---|
| Frontend | React.js, Vite, CSS |
| Backend | Java, Spring Boot |
| Build Tool | Maven |
| API Communication | REST APIs |
| Security | Spring Security, JWT |
| Database | MySQL |
| Database Hosting | Aiven MySQL |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |
| Version Control | Git and GitHub |

## 6. System Architecture

MapFinance follows a client-server architecture. The React frontend communicates with the Spring Boot backend through REST APIs. The backend handles application logic, authentication, authorization, and database operations. MySQL stores the application data.

```text
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
```

## 7. Project Structure

```text
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
```

This is a high-level overview of the repository. Refer to the source folders for the complete implementation.

## 8. Database Design and Connectivity

MapFinance uses a relational MySQL database hosted on Aiven. The database supports the application's financial management features.

### Main Logical Entities

- **User:** Stores account and authentication-related information.
- **Category:** Organizes financial records into categories.
- **Transaction:** Stores income and expense records.
- **Budget:** Stores budget limits and associated category information.
- **Goal:** Stores financial targets and progress information.

The Spring Boot backend connects to MySQL using the configured database connection and MySQL JDBC driver. Database settings are provided through application configuration and environment variables.

The actual table names, columns, and relationships are defined by the database schema implemented in the project.

## 9. User Interface and Responsiveness

The frontend is developed using React and Vite. The interface is organized into reusable components and pages for the dashboard, transactions, budgets, goals, reports, profile, and administration.

The UI/UX design focuses on:

- Consistent styling across user and admin pages.
- Clear navigation and readable layouts.
- Forms for entering and managing financial data.
- Dashboard summaries for important financial information.
- Responsive layouts for supported desktop and mobile screen sizes.

## 10. Requirements

The following software and services are required to run the project:

- Java JDK compatible with the backend configuration.
- Maven, or the Maven Wrapper if included.
- Node.js and npm.
- Access to a MySQL database.
- Git.
- A code editor such as Visual Studio Code.

## 11. Setup and Running Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/ankit-1010/Java-Project.git
cd Java-Project
```

### Step 2: Configure the Backend

Open the `backend` directory and refer to `backend/.env.example` for the required configuration variables.

Configure the database connection details, JWT secret, and any other required settings using the configuration method supported by the application. Ensure that the MySQL database is accessible.

Run the backend from the `backend` directory:

```bash
mvn spring-boot:run
```

If a Maven Wrapper is included, you can use it instead of installing Maven separately.

### Step 3: Configure the Frontend

Open a separate terminal in the project root and run:

```bash
cd frontend
npm install
```

Refer to `frontend/.env.example` for the required frontend environment variables. Configure the API base URL to point to the backend instance you want to use.

Start the frontend development server:

```bash
npm run dev
```

Open the local URL displayed in the terminal by Vite. Both the frontend and backend must be running and configured correctly for API-dependent features to work.

## 12. Deployment

MapFinance uses the following deployment services:

- **Frontend:** Vercel
- **Backend:** Render
- **Database:** Aiven MySQL

The frontend must use the correct backend API URL. The backend hosting environment must have the required database configuration, JWT secret, and appropriate CORS settings.

## 13. Code Quality and Security

The project separates the frontend and backend to organize application responsibilities and improve maintainability.

Security-related configuration should be stored in environment variables or the hosting provider's secret settings. Never commit real `.env` files, database passwords, JWT secrets, or administrator credentials to GitHub.



## 14. Conclusion

MapFinance is a full-stack personal finance management application that brings together frontend development, Java backend development, database connectivity, security, and deployment. It is designed to help users organize transactions, manage budgets, and monitor financial goals while demonstrating important concepts in web application development.

