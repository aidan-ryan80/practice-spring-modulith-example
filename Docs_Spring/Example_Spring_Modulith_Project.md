### Runtime Configuration:
```yaml
server:
  port: 8085

spring:
  datasource:
    url: jdbc:h2:mem:modulith_db
    username: sa
    password:
    driverClassName: org.h2.Driver
  h2:
    console:
      enabled: true
      path: /h2-console
  jpa:
    hibernate:
      ddl-auto: create-drop
```
### Chart for spring startup chain
```java
mvn spring-boot:run
        │
        ▼
Spring Boot Maven Plugin
        │
        ▼
java de.codecentric.spring_modulith_example.App
        │
        ▼
App.main()
        │
        ▼
SpringApplication.run()
        │
        ▼
Spring Boot starts application context
        │
        ▼
Embedded web server starts (port 8085)
```
### Calling API Endpoints
##### Product IDs (for listing products by IDs)
```bash
curl "http://localhost:8085/catalog?pageNumber=0"
```
##### Product Info
```bash
curl "http://localhost:8085/catalog/products/1"
```
##### Catalog Search By Name and Description
```bash
curl "http://localhost:8085/catalog/search/by/nameAndDescription?name=Produkt&description=&pageNumber=0""
```
##### Catalog Search By Max Price (listing products with a max price constraint)
```bash
curl "http://localhost:8085/catalog/search/by/maxPrice?price=200&pageNumber=0"
```
##### Check Stock (for specific product using the product ID)
```bash
curl "http://localhost:8085/inventory/stock/1"
```
##### Out Of Stock Products
```bash
curl "http://localhost:8085/catalog/products/outOfStock"
```
##### Add Stock (add to the inventory of a specific product by ID)
```bash
curl -X PUT "http://localhost:8085/inventory/stock/2?quantity=100"
```
##### Purchase (purchase a specific product by ID from the inventory)
```bash
curl -X POST "http://localhost:8085/inventory/stock/1?purchaseQuantity=100"
```
### Things to Investigate
- What are decorators called in Java and do they work the same way as they do in Python?
- What is a Spring Bean in the Spring framework?
##### Module structure
- Each module has its own controller, model, repository, and events?
- What is a repository and event inside of a module?
##### Testing
- How does maven execute the tests?
- Where are the tests located?
- How do the integration tests work?
- How can we create new integration or unit tests?
##### DevOps
- What would a simple CI pipeline look like for our project?
- Should we prepare a Dockerfile for our project? Or Docker compose instead?
- Should we use GitHub Actions during the project to run the integration tests that verify the modular structure?
- Should we implement some type of application logging? How would the `application.yaml` file be used for this?
- Should we create a bash script so that running everything takes a single command?
- What are the following commands for the CI pipeline suggested by ChatGPT?
```
checkout repo
↓
mvn clean compile
↓
mvn test
↓
mvn package
↓
produce runnable jar
```
- Analyze this example CI flow from ChatGPT:
```
code push
↓
CI pipeline runs
↓
build jar
↓
run tests
↓
artifact produced
```