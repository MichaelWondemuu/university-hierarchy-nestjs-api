# University Hierarchy API

## **Overview**

This project provides a RESTful API to manage a university's hierarchical structure using **NestJS**. It allows for the creation, updating, retrieval, and deletion of academic positions, organized in a parent-child hierarchy. The top-level position is the **University President**, and every level below reports to its immediate superior in the hierarchy.

----------

## **Features**

-   **Position/Role Management**:
    -   Add new positions with parent-child relationships.
    -   Update existing positions with new details.
    -   Delete positions and their hierarchy.
-   **Hierarchical Data Retrieval**:
    -   Retrieve positions as a tree structure.
    -   Fetch all child positions of a specific node.
    -   Get a detailed view of a single position.
-   **Testing and Documentation**:
    -   Swagger integration for API testing at [http://localhost:3000/api](http://localhost:3000/api).
    -   Unit tests for controllers.

----------

## **Hierarchy Example**
```
`University President
├── Institute of IoT
│   ├── School of Computing
│   │   ├── Department of Computer Science
│   │   │   ├── Teacher A
│   │   │   └── Teacher B
│   │   ├── Department of Software Engineering
│   │       ├── Teacher C
│   │       └── Teacher D
│   ├── School of Electrical and Mechanical
│   │   ├── Department of Electrical Engineering
│   │   │   ├── Teacher E
│   │   │   └── Teacher F
│   │   ├── Department of Mechanical Engineering
│   │       ├── Teacher G
│   │       └── Teacher H
│   ├── School of Civil
│       ├── Department of COTOM
│       │   ├── Teacher I
│       │   └── Teacher J
│       └── Department of Civil Engineering
│           ├── Teacher K
│           └── Teacher L
├── Institute of Social Science
│   ├── School of Humanities
│   │   ├── Department of History
│   │   │   ├── Teacher M
│   │   │   └── Teacher N
│   │   ├── Department of Literature
│   │       ├── Teacher O
│   │       └── Teacher P
│   ├── School of Behavioral Studies
│   │   ├── Department of Psychology
│   │   │   ├── Teacher Q
│   │   │   └── Teacher R
│   │   ├── Department of Sociology
│   │       ├── Teacher S
│   │       └── Teacher T
│   ├── School of Social Policy
│       ├── Department of Public Policy
│       │   ├── Teacher U
│       │   └── Teacher V
│       └── Department of Political Science
│           ├── Teacher W
│           └── Teacher X` 
```
----------

## **Technical Requirements**

-   **Backend**:
    -   **Framework**: NestJS (version >= 9)
    -   **Database**: PostgreSQL (Recommended) or SQL Server
    -   **ORM**: TypeORM 
    -   **Testing**: Jest for unit testing
    -   **API Documentation**: Swagger
    - ---
-   **Database Model**:
    
   | **Column**    | **Type** | **Description**                                                |
| ------------- | -------- | -------------------------------------------------------------- |
| `id`          | `uuid`    | Unique identifier for each position.                           |
| `name`        | `string` | Name of the position (e.g., "School of Computing").            |
| `description` | `string` | Details or information about the position.                     |
| `parentId`    | `uuid`    | ID of the parent position (null for the root position).        | |
    

----------

## **Installation**

### 1. Clone the Repository


`git clone https://github.com/MichaelWondemuu/university-hierarchy-nestjs-api.git
cd university-hierarchy-nestjs-api` 
### or install by your self
`$ npm i -g @nestjs/cli
$ nest new university-hierarchy-nestjs-api`

### 2. Install Dependencies


`npm install` 

### 3. Set Up the Database

-   Create a database named `orga_structure` in your PostgreSQL or SQL Server instance.

### 4. Start the Application


`npm start` 

----------

## **Usage**

### API Endpoints

#### 1. **Add a Position**

-   **POST** `/positions`
-   **Body**:
    
    
    `{
      "name": "School of Computing",
      "description": "A school focusing on computing technologies",
      "parentId": "GUID of Institute of IoT"
    }` 
    

#### 2. **Update a Position**

-   **PUT** `/positions/:id`
-   **Body**:
        
    `{
      "name": "Updated Position Name",
      "description": "Updated Description",
      "parentId": "GUID of new parent position"
    }` 
    

#### 3. **Get a Single Position**

-   **GET** `/positions/:id`

#### 4. **Get All Positions in Tree Format**

-   **GET** `/positions/tree`

#### 5. **Get All Children of a Position**

-   **GET** `/positions/:id/children`

#### 6. **Delete a Position**

-   **DELETE** `/positions/:id`

----------

## **Testing and API Documentations**

### Swagger

Access API documentation and test endpoints using Swagger at [http://localhost:3000/api](http://localhost:3000/api).

### Postman

Use Postman to test API requests and responses by importing the provided collection (if available).

### Unit Tests

Run unit tests for controllers:

`npm run test` 

----------

## **Best Practices**

-   **Separation of Concerns**: Use modular development with NestJS modules.
-   **Maintainability**: Follow clean architecture principles.
-   **Scalability**: Support unlimited hierarchical depth.

----------

## **Reading Materials**

### **Books**

-   _Patterns, Principles, and Practices of Domain Driven Design_ (Scott Millett, Nick Tune)
-   _Clean Architecture: A Craftsman’s Guide to Software Structure and Design_ (Robert C. Martin)
-   _Domain Driven Design Reference_ (DDD Reference)
-   _Domain Driven Design Quickly_ (DDD Quickly)

### **Links**

#### **Backend**

-   [NestJS Documentation](https://nestjs.com/)
-   DDD, Hexagonal, Onion, Clean, CQRS
-   [Command Query Responsibility Segregation (CQRS)](https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs)

#### **Database**

-   [PostgreSQL Documentation](https://www.postgresql.org/docs/)
-   [SQL Server Documentation](https://docs.microsoft.com/en-us/sql/sql-server/)

## **Authors**

- @demeke-getaneh
- @Melese
- @michaelwondemuu ([GitHub Profile](https://github.com/MichaelWondemuu))
