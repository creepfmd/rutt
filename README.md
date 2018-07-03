# rutt
Queue system with REST

# starting
System runs in rancher environment
## 1. redis
+ redis - cluster
+ redis-cleaner
```
AMQP_URL=amqp://mqadmin:mqadmin@dev-rabbit-1//
```
## 3. mongo
Mongo cluster
## 3. rutt-base
Every container could exist in multiple instances behind ha-proxy
+ splitter
+ queuer
```
AMQP_URL=amqp://mqadmin:mqadmin@dev-rabbit-1//
EXPIRE_TIME=120
MONGO_URL=mongodb://mongo:27017
REDIS_URL=redis:6379
```
+ logger
```
MONGO_URL=mongodb://mongo:27017
```
+ action-scripter
## 4. frontend
## 5. director-starter
Specify label
```
cron.schedule = 0 */5 * ? * *
```
Specify ENV
```
ACTION_SCRIPTER_URL=http://action-scripter:8081/webhook/
ELASTICSEARCH_URL=elasticsearch:9200
AMQP_URL=amqp://mqadmin:mqadmin@dev-rabbit-1//
GIT_URL=gitlab-container-registry:4567
LOGGER_URL=http://logger:8084/
RANCHER_KEY=
RANCHER_USER=
RANCHER_STACKS_URL=http://rancher:8080/v2-beta/projects/1a5/stacks
MONGO_URL=mongodb://mongo:27017
REDIS_URL=redis:6379
SPLITTER_URL=http://splitter:8082/
```
## 6. director
Directors are starting automatically via crontab for every system in mongo collection.
