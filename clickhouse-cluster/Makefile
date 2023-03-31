.PHONY: config
config:
	rm -rf clickhouse01 clickhouse02 clickhouse03 zookeeper
	mkdir -p clickhouse01/{etc,data,log} clickhouse02/{etc,data,log} clickhouse03/{etc,data,log} zookeeper/{datalog,data,log,logs}
	IP=172.23.0.11 SHARD=1 envsubst < config.xml > clickhouse01/etc/config.xml
	IP=172.23.0.12 SHARD=2 envsubst < config.xml > clickhouse02/etc/config.xml
	IP=172.23.0.13 SHARD=3 envsubst < config.xml > clickhouse03/etc/config.xml
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
