# A love letter to message queuing

https://2025.pycon.it/en/event/a-love-letter-to-messaging-celebrating-rabbitmqs-journey

Speaker: [Lovisa Johansson](https://www.linkedin.com/in/lovisa-johansson-a6836733/)

---

https is sync, requires response

Queues, and microservices, allow to use different languages

One can fail without affecting the others

---

Many message brokers

- Apache Kafka has its own protocol
- AMQP is a standard messaging protocol (like HTTP for the web)

2007 was one of the first implementations of AMQP

Free and open source from the start.

Celery can be used to handle background tasks

---

Cloud AMPQ

---

Routing keys with exchange topic

bind a queue with various types of wildcards 

---

quorum queues

use raft consensus algorithm

---

message queues -> single consumption

message streams -> persistence, multi consumer access

