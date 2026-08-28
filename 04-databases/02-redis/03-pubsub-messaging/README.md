# Module 24: Redis Pub/Sub and Messaging

Understand Redis Pub/Sub as low-latency fan-out and Redis Streams as a more durable stream primitive. Use [Redis Pub/Sub](https://redis.io/docs/latest/develop/pubsub/), [Redis Streams](https://redis.io/docs/latest/develop/data-types/streams/), and the dedicated Module 29 messaging work for Kafka/RabbitMQ.

## Practice Deliverable

Publish and consume a TeamOps notification event. Document whether the feature tolerates message loss. If durable consumption, retries, consumer groups, or replay matter, use a Stream or defer to Module 29 rather than claiming Pub/Sub provides those guarantees.

## Completion Criteria

- [ ] Explain publisher, channel/stream, subscriber/consumer, and fan-out behavior.
- [ ] Define delivery expectations and failure behavior.
- [ ] Make the consumer idempotent where duplicate work is possible.
- [ ] Record logs/metrics for publish and consume failures.

## Common Mistakes

Using Pub/Sub for durable jobs, assuming disconnected subscribers receive old messages, no retry/dead-letter design, consumers with non-idempotent side effects, and treating Redis messaging as a substitute for service boundaries.

## Next

Continue to [Module 25](../04-rate-limiting/).
