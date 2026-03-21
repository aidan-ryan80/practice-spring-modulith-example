## Chart for spring boot startup chain
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