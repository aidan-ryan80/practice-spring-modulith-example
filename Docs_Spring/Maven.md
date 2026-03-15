### Apache Maven is a build tool used for Java projects
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
##### Standard maven layout
- Standard maven layout includes config files for the runtime.
- Standard maven layout:
```bash
src  
├── main  
│ ├── java application source code  
│ └── resources config files  
│  
└── test  
└── java tests
```
##### Maven project configuration file
- The Maven project configuration file is called `pom.xml` (project object model)
- Lists project information, Dependencies, Build instructions, and test configuration
### Maven Commands
##### Install dependencies from pom.xml, compile the code, and run tests
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
##### Compile a project
```bash
mvn compile
```