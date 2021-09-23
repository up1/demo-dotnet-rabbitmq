# demo-dotnet-rabbitmq
* Start with background service

```
$docker-compose up -d rabbitmq
$docker-compose up -d consumer
$docker-compose ps

// Scale consumer
$docker-compose up -d --scale consumer=5
```
