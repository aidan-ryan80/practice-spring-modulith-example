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