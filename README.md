# Spring Kafka Kotlin Producer & Consumer

This project has consumer and producer examples of the simplest possible
spring kafka implementation using defaults and might have some other
examples in the future. 

### 1. Kafka server on my MAC
#export DOCKER_HOST_IP=Kierans-MacBook-Pro.local

### 2. Launch Kafka in docker
```
docker-compose up -d
```

### 2. Start the Producer(REST API) and Consumer (Topic : simple-message-topic)
```
./gradlew build && ./gradlew bootRun
```

### 3. Post some messages to the API tied to the producer via curl
```
curl -X POST http://localhost:8080/api/message -H "Content-Type: application/json" -d '{"test"}'
```

### 4. Observe the Consumer
```
2020-10-14 10:33:21.364  INFO 71300 --- [nio-8080-exec-1] o.a.kafka.common.utils.AppInfoParser     : Kafka version : 2.0.1
2020-10-14 10:33:21.364  INFO 71300 --- [nio-8080-exec-1] o.a.kafka.common.utils.AppInfoParser     : Kafka commitId : fa14705e51bd2ce5
2020-10-14 10:33:21.377  INFO 71300 --- [ad | producer-1] org.apache.kafka.clients.Metadata        : Cluster ID: s2jy226ZSeeDoWwN5ifNVA
2020-10-14 10:33:21.447  INFO 71300 --- [ntainer#0-0-C-1] i.r.springkafkakotlin.KotlinConsumer     : got message: {"test"}
```

#### Ref and Credit:
https://dev.to/thegroo/simplest-spring-kafka-producer-and-consumer-kotlin-version-dn8 ##
