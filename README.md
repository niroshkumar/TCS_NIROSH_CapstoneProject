# TCS_NIROSH_CapstoneProject
Final version of capstone e-commerce project 


Please follow all the prerequisites to run the application:

STEP-1: Create the network by running the below commands
--------------------------------------------------------
docker network create ecommerce-net


MYSQL docker image build:
-------------------------
RUN===> docker-compose-MySQL.yml

Other apps docker images build and deploy:
-------------------------------
Capstone Project\eureka-server\docker-compose.yml
  --docker-compose build
  --docker-compose up

Capstone Project\Inventory-Service\docker-compose.yml
 --docker-compose build
  --docker-compose up

Capstone Project\Order-Processing-Service\
 --docker-compose build
  --docker-compose up

Capstone Project\Payment-Service\
 --docker-compose build
  --docker-compose up

Capstone Project\Product-Catalog-Service\
 --docker-compose build
  --docker-compose up

Capstone Project\Customer-Service\docker-compose.yml
 --docker-compose build
 --docker-compose up

Capstone Project\apigateway\docker-compose.yml
 --docker-compose build
 --docker-compose up


Capstone Project\docker-compose-mysql.yml
 --docker-compose -f  .\docker-compose-mysql.yml up

Capstone Project\docker-compose-kafka.yml
 --docker-compose -f  .\docker-compose-kafka.yml up


Topic creations:
-------------------
docker exec -it kafka kafka-topics --create --topic OrderPlaced --bootstrap-server localhost:8192 --partitions 1 --replication-factor 1
docker exec -it kafka kafka-topics --create --topic InventoryUpdated --bootstrap-server localhost:8192 --partitions 1 --replication-factor 1
docker exec -it kafka kafka-topics --create --topic PaymentMade --bootstrap-server localhost:8192 --partitions 1 --replication-factor 1

Microservices Docker images end-points
================================
http://localhost:8090/products
http://product-container:8090

http://localhost:8093/inventory
http://inventory-container:8093

http://localhost:8092/orders
http://order-container:8092

http://localhost:8094/payments
http://payment-container:8094 

http://localhost:8091/customers
http://customer-container:8091 

ERUKA
======
http://localhost:8761
http://eureka-server:8761/eureka/

SWAGGER UI
==============

http://localhost:8090/swagger-ui/index.html
http://localhost:8091/swagger-ui/index.html
http://localhost:8092/swagger-ui/index.html
http://localhost:8093/swagger-ui/index.html
http://localhost:8094/swagger-ui/index.html

