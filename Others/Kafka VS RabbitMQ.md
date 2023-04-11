## What is Kafka
- Open source distributed event streaming platform that applies the pub/sub pattern, facilitating high throughput
- Kafka appends messages to the log and leaves them there, where they remain until customer reads it or reaches its retention limit
- Kafka employs a "pull-based" approach, letting users request message batches from specific offsets

## What is RabbitMQ
- Open source distributed message broker that facilitates efficient message delivery in complex routing scenarios
- Runs as a cluster of nodes where the queues are distributed across the nodes, replicated for high availability and fault tolerance, is a queue based architecture
- Employs a "push model" and prevents overwhelming users via the consumer configured prefetch limit
- This model is ideal for low-latency messaging

## What is Kafka used for
- best used for streaming from A to B without restoring to complex routing, but with maximum throughput
- also ideal for event sourcing, stream processing
- bottom line can be used for storing, reading, re-reading and analyzing streaming data.
- ideal for routinely audited systems or that store their messages permanently, as kakfa stores their messages in the log
- truly shines with real-time processing and analyzing data

## What is RabbitMQ used for
- Process high-throughput and reliable background jobs, plus integration and intercommunication between and within applications
- Perfect for web servers that need rapid request-response 
- It also shares loads between workers under high load

Too much info, refer here:
- https://www.simplilearn.com/kafka-vs-rabbitmq-article#:~:text=Data%20Usage,logging%20statistics%2C%20and%20system%20activity.
- https://www.projectpro.io/article/kafka-vs-rabbitmq/451#:~:text=Kafka%20vs%20RabbitMQ%20%2D%20Performance,-High%20throughput%20is&text=Kafka%20is%20capable%20of%20processing,more%20resources%20to%20do%20so.