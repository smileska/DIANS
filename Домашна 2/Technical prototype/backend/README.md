# MSE Analytics Frontend

This is a Next.js application for visualizing Macedonian Stock Exchange data.

## Frontend Setup

### Prerequisites

- Node.js (version 18 or higher)
- npm (comes with Node.js)

### Installation

1. Navigate to the project directory:
```bash
cd mse-analytics
```

2. Install the required dependencies:
```bash
npm install
```

Note: This will install all dependencies listed in `package.json`, including:
- Next.js
- React
- Recharts for data visualization
- Lucide React for icons
- Tailwind CSS for styling
- shadcn/ui components

### Development Server

To run the development server:
```bash
npm run dev
```

The application will start on `http://localhost:3000`. You can open this URL in your browser to view the application.

## Backend Setup

### Prerequisites

- Java 17 or higher
- Maven
- PostgreSQL database server

### Database Configuration

1. Create a PostgreSQL database for the project
2. Open `src/main/resources/application.properties`
3. Configure the following properties:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/your_database_name
spring.datasource.username=your_database_username
spring.datasource.password=your_database_password
```

Additional configuration properties:
```properties
# Server port
server.port=8090

# JPA/Hibernate properties
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# Logging
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR
```

### Running the Application

1. Make sure PostgreSQL is running and the database is created
2. Start the Spring Boot application:
   - Using Maven: `mvn spring-boot:run`
   - Or run `Project1Application.java` from your IDE

The backend API will be available at `http://localhost:8090`

## Common Issues

### Frontend
- If you encounter an out-of-memory error during development, the project is already configured with increased memory allocation in the `dev` script. If you still experience issues, you can manually increase the memory limit by modifying the `dev` script in `package.json`.

### Backend
- Database Connection: Ensure that PostgreSQL is running and accessible
- Port Conflicts: If port 8090 is already in use, you can change the `server.port` in `application.properties`
- Database Migration: If you need to reset the database, set `spring.jpa.hibernate.ddl-auto=create` temporarily

## Features

- Company search functionality
- Real-time data visualization
- Interactive charts using Recharts
- Responsive design with Tailwind CSS
- Modern UI components from shadcn/ui
- REST API endpoints for market data
- Automated data collection from MSE

## API Endpoints

- `GET /api/company/all` - Get all companies
- `GET /api/company/{id}` - Get company by ID
- `GET /api/data/all` - Get all market data
- `GET /api/data/{id}` - Get market data by ID
