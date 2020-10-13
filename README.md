# Spring Kafka Kotlin

This project has consumer and producer examples of the simplest possible
spring kafka implementation using defaults and might have some other
examples in the future. 

This project was created for a introductory tutorial of using spring-kafka 
with Kotlin written here: 

// TODO ADD URL WHEN PUBLISHING POST


## https://dev.to/thegroo/simplest-spring-kafka-producer-and-consumer-kotlin-version-dn8 ##
# 1. Kafka server on my MAC
export DOCKER_HOST_IP=Kierans-MacBook-Pro.local

docker-compose up -d

# 2. Start the Producer(REST API) and Consumer (Topic)
./gradlew build && ./gradlew bootRun

# 3. Post some messages (POST to API) via curl
for n in 1 2 3 4 5 6 7 8 9; do curl -X POST http://localhost:8080/api/message -H "Content-Type: application/json" -d '{
  "users": [
    {
      "userId": 1,
      "firstName": "Krish",
      "lastName": "Lee",
      "phoneNumber": "123456",
      "emailAddress": "krish.lee@learningcontainer.com"
    },
    {
      "userId": 2,
      "firstName": "racks",
      "lastName": "jacson",
      "phoneNumber": "123456",
      "emailAddress": "racks.jacson@learningcontainer.com"
    },
    {
      "userId": 3,
      "firstName": "denial",
      "lastName": "roast",
      "phoneNumber": "33333333",
      "emailAddress": "denial.roast@learningcontainer.com"
    },
    {
      "userId": 4,
      "firstName": "devid",
      "lastName": "neo",
      "phoneNumber": "222222222",
      "emailAddress": "devid.neo@learningcontainer.com"
    },
    {
      "userId": 5,
      "firstName": "jone",
      "lastName": "mac",
      "phoneNumber": "111111111",
      "emailAddress": "jone.mac@learningcontainer.com"
    }
  ]
}'; done
