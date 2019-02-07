FROM rabbitmq:3.7.11-management

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
  curl \
  && rm -rf /var/lib/apt/lists/*

RUN rabbitmq-plugins enable --offline rabbitmq_management && \
  rabbitmq-plugins enable --offline rabbitmq_shovel && \
  rabbitmq-plugins enable --offline rabbitmq_shovel_management

COPY ./rabbitmq.config /etc/rabbitmq/
COPY ./definitions.json /tmp/

COPY ./entrypoint.sh /tmp
ENTRYPOINT ["/bin/bash", "/tmp/entrypoint.sh"]

CMD ["rabbitmq-server"]