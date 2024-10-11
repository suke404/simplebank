# Simple Bank Project
This is a personal project to design, develop and deploy a backend web service from scratch.

My goal is to create a functional APIs, and at the same time learn more about the tools for backend development.

The programming language that I will be using to develop the service will be **Golang**

## Simple bank service
This project will provide APIs for the frontend to do the following:
+ Create and manage bank accounts, which are composed of owner's name, balance, and currency.
+ Record all balance changes to each of the accounts. So every time some money is added to or subtracted from the account, and account entry record will be created.
+ Perform a money transfer between 2 accounts. This should happan within a transaction, so that either both accounts' balance are updated sucessfully or none of them are.

## Requirements
- Docker
- Go
- [migrate](https://github.com/golang-migrate/migrate) (for database migrations)
- [sqlc](https://github.com/kyleconroy/sqlc) (for generating type-safe SQL code)
- [mockgen](https://github.com/golang/mock) (for generating mocks for testing)

## Setup

### 1. Running PostgreSQL with Docker
To start a PostgreSQL container:
```bash
docker run --name postgres12 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:12-alpine
+ start postgres container:
```

### 2. Creating the database
```
docker exec -it postgres12 createdb --username=root --owner=root simple_bank
```
Dropping the database
```
docker exec -it postgres12 dropdb simple_bank
```

### 3. Database Migrations
To apply all database migrations:
```
migrate -path db/migration -database "postgresql://root:secret@localhost:5432/simple_bank?sslmode=disable" -verbose up
```
To revert the last database migration:
```
migrate -path db/migration -database "postgresql://root:secret@localhost:5432/simple_bank?sslmode=disable" -verbose down
```

### 4. Generate SQL Code
To generate the Go code from SQL queries using sqlc:
```
sqlc generate
```
### 5. Generate mock database
.
.
.

make postgres
```
+ Create simple_bank database:
```
make createdb


## GitHub Actions

This project uses GitHub Actions for Continuous Integration (CI) to automate testing and ensure code quality. Each time a commit is pushed, the tests are automatically executed. Here's how it's set up:

### CI Workflow

- **Linting**: Code is checked for stylistic and syntactical errors to ensure it follows the project's coding standards.
- **Testing**: Unit tests are run using go built-in `testing` package.

Current task:
Implementing the Mock DB for testing HTTP API in Go...
