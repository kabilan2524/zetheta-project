# Reflection
The project demonstrates that fintech engineering is primarily about correctness under concurrency and failure, not merely request throughput. The central design trade-off is between strong transactional boundaries and distributed scale. The ledger remains authoritative while Kafka provides decoupling for downstream work.

The key lessons are durable idempotency, the transactional outbox, OCC correctness, explicit performance budgets and FMEA-driven reliability. Sharding increases capacity but creates routing and cross-shard complexity, so the design prefers account ownership as the distribution boundary and requires explicit handling of hot merchants.

The final architecture should be revised from benchmark evidence. Assumptions about throughput per shard, instance count and monthly cost must be tested rather than treated as facts.
