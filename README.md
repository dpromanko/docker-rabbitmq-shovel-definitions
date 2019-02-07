I ran into this [issue](https://github.com/rabbitmq/rabbitmq-shovel/issues/13) where every time I tried to import RabbitMQ definitions.json that had shovels at container startup the container would die.

To work around this you need to import shovel definitions (or all definitions as I do in this example) after everything is started. You can see how I do this in `entrypoint.sh`.

To run this demo:
```sh
docker-compose up --build
```