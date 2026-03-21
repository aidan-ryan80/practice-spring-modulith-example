### Apache Maven is a build tool used for Java projects
##### Standard maven layout
- Standard maven layout includes config files for the runtime.
- Standard maven layout:
```bash
my-modulith-project/
├── pom.xml                      <-- The "Project Object Model" (Heart of Maven)
├── src/                         <-- All your source code lives here
│   ├── main/                    <-- Production code
│   │   ├── java/                <-- Your .java files (Package folders)
│   │   │   └── com/company/app/
│   │   │       ├── inventory/   <-- Module A
│   │   │       ├── shipping/    <-- Module B
│   │   │       └── Main.java    <-- Entry point
│   │   └── resources/           <-- Config files, SQL, static assets
│   └── test/                    <-- Test code
│       ├── java/                <-- Your JUnit tests
│       └── resources/           <-- Test-only config files
└── target/                      <-- GENERATED folder (Where your .jar ends up)
```
##### `target/` directory
- Maven compiles and generates files and puts them into `target/`
- Example contents:
```bash
target/  
├── classes/ compiled .class files  
├── test-classes/ compiled test classes  
├── generated-sources/  
├── surefire-reports/ test reports  
└── *.jar packaged application
```
##### Maven project configuration file
- The Maven project configuration file is called project object model => `pom.xml`
- Defines Dependencies, Plugins, Metadata, Build instructions, and test configuration
### Maven Commands
##### Table for common commands:

|**Command**|**What it does**|**Python Equivalent (Roughly)**|
|---|---|---|
|`mvn clean`|Deletes the `target/` folder|`rm -rf __pycache__`|
|`mvn compile`|Checks for syntax errors and makes `.class` files|(No direct equivalent)|
|`mvn test`|Runs all your unit tests|`pytest`|
|`mvn package`|Runs tests and creates the `.jar` file|`pip install .` or `build`|
|`mvn install`|Puts your JAR in a local cache for other projects to use|`pip install -e .`|
##### Deletes the `target/` directory, compiles the code, installs dependencies, and runs tests
```bash
mvn clean install
```
##### Run the Spring Boot application
```bash
mvn spring-boot:run
```
##### Execute tests after deleting build artifacts from target directory
```bash
mvn clean test
```