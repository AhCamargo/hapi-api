## Application created with Hapi.js, together Repository Pattern. 

- Creating the database(s)

## --- MongoDB
docker run  --name product-mongodb -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=alc123 -d mongo:4

- *Interface GUI*
docker run --name product-mongoclient -p 3030:3000 --link product-mongodb:product-mongodb -d mongoclient/mongoclient
  
## create user and create the database in the mongoDB
 docker exec -it product-mongodb \
   mongo --host localhost -u admin -p alc123 --authenticationDatabase admin \
   --eval "db.getSiblingDB('product').createUser({user:'ahcamargo', pwd: 'alc123', roles: [{role: 'readWrite', db: 'product'}]})" 

- Method of Creation
  Utilized Hapi.js for construction of API, with together the designer pattern Repository

## Plus of Application
  * Databases in Docker
  * Framework Hapi.js
  * Repository Pattern
    
