# Kafka in Docker

Kafka using docker, with a single node.
Inspired by https://github.com/codingharbour/kafka-docker-compose and https://github.com/confluentinc/cp-docker-images

## Start 
`docker-compose up -d`

## Remove
`docker-compose rm`

### Connect to kafka client
`docker exec -it sn-kafka /bin/bash`

### Create topic

```
    kafka-topics --bootstrap-server localhost:9092 \
    --create --topic TOPIC_NAME \
    --partitions 1 \
    --replication-factor 1
```

### List topics
`kafka-topics --bootstrap-server localhost:9092 --list`

### Produce Message
`kafka-console-producer --broker-list localhost:9092 --topic TOPIC_NAME --property "parse.key=true" --property "key.separator=:"`

### Consume message
`kafka-console-consumer --bootstrap-server localhost:9092 --topic TOPIC_NAME`