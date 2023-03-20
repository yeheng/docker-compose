.PHONY: config
config:
	rm -rf clickhouse01 clickhouse02 clickhouse03 zookeeper
	mkdir -p clickhouse01/{etc,data,log} clickhouse02/{etc,data,log} clickhouse03/{etc,data,log} zookeeper/{datalog,data,log,logs}
	REPLICA=01 SHARD=01 envsubst < config.xml > clickhouse01/etc/config.xml
	REPLICA=02 SHARD=01 envsubst < config.xml > clickhouse02/etc/config.xml
	REPLICA=03 SHARD=02 envsubst < config.xml > clickhouse03/etc/config.xml
	cp users.xml clickhouse01/etc/users.xml
	cp users.xml clickhouse02/etc/users.xml
	cp users.xml clickhouse03/etc/users.xml

.PHONY: up
up:
	docker-compose up -d

.PHONY: start
start:
	docker-compose start

.PHONY: down
down:
	docker-compose down
