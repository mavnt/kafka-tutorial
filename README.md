# kafka-tutorial

Mostly from https://kafka.apache.org/quickstart-docker, using [Bitnami images](https://hub.docker.com/r/bitnami/kafka/).

Shell 0:

``` bash
docker-compose up
```

Shell 1 - kafka:2-debian-10:

``` bash
kafka-topics.sh \
  --create --topic my-cool-topic \
  --zookeeper zookeeper:2181 \
  --partitions 4 \
  --replication-factor 1

kafka-topics.sh \
  --describe \
  --topic my-cool-topic \
  --zookeeper zookeeper:2181

kafka-console-producer.sh \
  --topic my-cool-topic \
  --bootstrap-server localhost:9092

# start typing

```

Shell 2 - kafka:2-debian-10:

``` bash
kafka-console-consumer.sh \
  --topic my-cool-topic \
  --from-beginning \
  --bootstrap-server localhost:9092
```

or

``` bash
kafka-console-consumer.sh \
  --topic my-cool-topic \
  --bootstrap-server localhost:9092
```
