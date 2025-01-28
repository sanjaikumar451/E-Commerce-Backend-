# Spring Boot CRUD API for Managing Stocks in E-commerce Shop

## Description
This project is a simple **Spring Boot CRUD API** that manages stock details for an online e-commerce shop. It provides RESTful endpoints to create, read, update, and delete stock information. It also connects to a MySQL database for persistent data storage.

## Features
- Add new stock items
- Retrieve all stock items
- Retrieve a stock item by ID
- Update stock details
- Delete stock items

---

## Requirements
Ensure you have the following installed:
- Java 17 or above
- Maven
- MySQL
- Spring Boot CLI (Optional)

---

## Dependencies
This project uses the following dependencies from **Spring Initializr**:

1. **Spring Web** (For building REST APIs)
2. **Spring Data JPA** (For database interaction)
3. **MySQL Driver** (For connecting to MySQL database)
4. **Spring Boot DevTools** (Optional, for live reloading during development)

---

## Installation and Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/spring-stock-crud-api.git
   cd spring-stock-crud-api
   ```

2. Configure the MySQL Database:
   - Create a database named `ecommerce_db` in MySQL.
   - Open `src/main/resources/application.properties` and update the database configuration:

     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
     spring.datasource.username=<your-mysql-username>
     spring.datasource.password=<your-mysql-password>

     spring.jpa.hibernate.ddl-auto=update
     spring.jpa.show-sql=true
     spring.jpa.properties.hibernate.format_sql=true
     ```

3. Build the project:

   ```bash
   mvn clean install
   ```

4. Run the application:

   ```bash
   mvn spring-boot:run
   ```

5. Access the API:
   - Base URL: `http://localhost:8080/api/stocks`

---

## API Endpoints

### 1. **Get All Stocks**
   - **Method**: `GET`
   - **URL**: `/api/stocks`
   - **Description**: Fetch all stock items.

### 2. **Get Stock by ID**
   - **Method**: `GET`
   - **URL**: `/api/stocks/{id}`
   - **Description**: Fetch a specific stock by its ID.

### 3. **Create a New Stock**
   - **Method**: `POST`
   - **URL**: `/api/stocks`
   - **Body**:
     ```json
     {
       "name": "Laptop",
       "quantity": 10,
       "price": 799.99
     }
     ```

### 4. **Update a Stock**
   - **Method**: `PUT`
   - **URL**: `/api/stocks/{id}`
   - **Body**:
     ```json
     {
       "name": "Gaming Laptop",
       "quantity": 8,
       "price": 899.99
     }
     ```

### 5. **Delete a Stock**
   - **Method**: `DELETE`
   - **URL**: `/api/stocks/{id}`

---

## Database Schema

The `stocks` table has the following schema:

| Column   | Type        | Description               |
|----------|-------------|---------------------------|
| `id`     | BIGINT      | Primary Key, Auto-Increment|
| `name`   | VARCHAR(255)| Name of the stock item    |
| `quantity`| INT        | Quantity of the stock item|
| `price`  | DECIMAL(10,2)| Price of the stock item   |

---


## Running Tests
To run unit tests:

```bash
mvn test
```

---

## Future Enhancements
- Add user authentication (e.g., Spring Security)
- Implement pagination and sorting for fetching stocks
- Add filtering capabilities based on price and availability

---
