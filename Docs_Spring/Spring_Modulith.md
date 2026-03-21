# Docs on Spring Modulith
### Folder Structure for modules
```bash
src/main/java/de/codecentric/app/
└── orders/
    ├── OrderController.java   <-- The API (Handles Requests)
    ├── OrderService.java      <-- The Logic (The "Brain")
    ├── OrderRepository.java   <-- The DB Gateway (Interface)
    └── Order.java             <-- The Model (The @Entity)
```

### Databases

##### 2. Setting up the "Database" (H2 Example)
Since you are using **Maven**, you don't download a database. You just tell the `pom.xml` you want it.

**In `pom.xml`:**
XML
```
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>
```

**In `src/main/resources/application.properties`:** This is all the config you need to make it act like SQLite (saving to a file):

Properties
```
# Tell Spring where to save the database file
spring.datasource.url=jdbc:h2:file:./data/my_modulith_db
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=

# Create tables automatically based on your @Entity classes
spring.jpa.hibernate.ddl-auto=update

# Let me see the SQL in the console (useful for debugging!)
spring.jpa.show-sql=true
```