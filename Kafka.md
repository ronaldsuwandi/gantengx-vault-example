Kafka is split into server and clients. They communicate to each other via high performance TCP protocol. It uses **custom protocol** for performance optimization.

Kafka Server run as a cluster of one or more servers. Kafka server is also called broker
- Some server form storage layer (kafka brokers)
- Other server may run Kafka Connect to import/export data stream
- Other server may run Kafka Streams or ksqlDB and so on
- Brokers require [[ZooKeeper]] (will be deprecated once [KIP-500](https://cwiki.apache.org/confluence/display/KAFKA/KIP-500%3A+Replace+ZooKeeper+with+a+Self-Managed+Metadata+Quorum) is ready for production - not yet rady for production use as of [[2022-09-05]]). -- **UPDATE:** as of **Kafka 3.3 [[2022-10-04]] ZooKeeper removal is now production ready**

Kafka is basically a distributed log system. Log in this case is not the output log, but the messages. It's a publisher subscriber and it has a guarantee of message ordering per partition level.

Events are organised into topics. Topics are always multi-producer and multi-subscriber. Unlike the traditional messaging (queue), once topic is consumed, it is not deleted allowing it to be replayed - topic logs can be stored indefinitely (default is 7 days) but can be configured per topic

Topics are [[Kafka partitions|partitioned]] and can be [[Kafka replication|replicated]]. Events with the same event key (e.g. customer or vehicle ID) are written to the same partition by default. Kafka guarantees that messages are ordered **in partition level**

> [!tip] Completely ordered events
> You can achieve a completely ordered events where all messages always comes in order. In this case using single partition is the only way but this will drastically limit the throughput
> 
> Usually when you need completely ordered events, it's only for the **subset** of the system. In that case, try to minimize the need for the single partition topic as much as possible so that it doesn't affect other part of the system

If consumer consume from a Consumer Group, it is guaranteed that each consumer from the group will never consume from the same partition hence avoiding scenario where we have multiple consumers consuming the same partitions and processed the same message multiple times (within consumer group)

> [!warning] Java client application
> When writing Java client application, you must also import **kafka** and not just **kafka-clients** otherwise the application won't be able to get any topic metadata from broker

Kafka has 5 core APIs
- Admin API to manage/inspect topics, brokers and other Kafka objects
- Producer API to publish messages to topics. See: [[Kafka Producer and Consumer]]
- Consumer API to subscribe to topics and process messages. See: [[Kafka Producer and Consumer]]
- Kafka Streams API to implement stream processing applications. It provides high level functions to process events streams like transformations, windowing, joining, etc
- Kafka Connect API to build and run data import/export connectors. It's essentially a consumer/producer application which the main job is to either read or write data from/to external system (it can also be used to read/write data from/to different topics)

## Kafka use cases
### Messaging - replace traditional message broker
- Better throughput, built-in partitioning, replication, and fault-tolerance which makes it a good solution for large scale message processing applications.
- Usually low throughput but requires low e2e latency
- Comparable to RabbitMQ and ActiveMQ
### Website Activity Tracking - initial goal of Kafka
- Each activity is published to a central topic with one topic per activity type
- Client can subscribe for real time processing, monitoring and loading into Hadoop for offline batch processing and reporting
- Activity tracking tends to be high volume
### Metrics - operational monitoring data
- [[C3|Confluent Control Center]] is [[Kafka Streams]] based application that keep track Kafka's own metrics in Kafka. It's kind of eating your own dogfood
### Log aggregation
- Equally good performance compared to Flume or Scribe
### Stream Processing
- 0.10 onwards Kafka comes with [[Kafka Streams]] library to make this easier
- [[ksqlDB]] is another abstraction on top of Kafka Streams to make stream processing simpler with SQL-like syntax
### Event Sourcing
- Application design where state changes are logged as a time-ordered sequence of records. Kafka's support for very large stored log data makes it an excellent backend for an application built in this style.
### Commit Log - serve as commit log for distributed system
- Log compaction helps achieve this feature
- Similar to Apache BookKeeper system

## Kafka basic configs
### Broker config
`num.recovery.threads.per.data.dir` used to handle log segments
- When starting normally, open each partition log segments
- When starting after failure, check and truncate each partition log segment
- When shutting down, to cleanly close segments

By default 1 thread/log directory is used and the threads are only used during startup/shutdown
- Reasonable to set large number of threads to paralellize operations
- This can mean **several hour difference** when restarting a broker with a large number of partitions

If the value is set to 8 and there are 3 paths specified in `log.dirs` then it's total of 24 threads

### Producer config
`acks`
- 0 = fire and forget
- 1 = leader will write and respond without waiting for all followers
- all (or -1) = wait for full set of ISR (in sync replicas) to respond). Guarantees no record lost as long as 1 ISR is active. Strongest guarantee
- See: [[Kafka message delivery semantics]]

`num.partitions` determines how many partitions. 

## Kafka hardware and tuning
- [[Kafka basic hardware and OS tuning]]
- [[Factors to consider for determining number of topic partitions in Kafka]]
- [[Kafka production concerns]]
- [[Kafka in Production]]

## Heartbeat
[KIP-62](https://cwiki.apache.org/confluence/display/KAFKA/KIP-62%3A+Allow+consumer+to+send+heartbeats+from+a+background+thread) allows Kafka heartbeat to be run on a separate thread. Available since 0.10 and this means that we can have request-response pattern (see: [[Request-response over Kafka Streams application architecture]]) because consumer can just perform `Poll` on demand. This is also available in librdkafka

## Consumer client
In [[Cassandra]], we send request to all nodes all the time. For Kafka, we only fetch from the leader, so how does client know where to perform the poll?
- Client caches partition leaders for all topics it subscribes
- When there is no data in the buffer, client issues FETCH requests to **all the leaders**
- FETCH may fail if the leader is being moved to another broker. In this case, client will fetch metadata instead
- Client also fetch metadata regularly from all leaders (there is a METADATA API)
- Each brokers have eventually consistent complete metadata
- Only brokers talks to ZooKeeper

## Log flush
`log.flush.interval`, `log.flush.interval.messages` and `log.flush.scheduler.interval.ms` are set to very high value for a reason. This is to let OS handle the flushing of pagecache into disk instead of letting Kafka Broker do it 

## Queued max request bytes
`queued.max.request.bytes` generally should be set to avoid OOM as shown in [KIP-72](https://cwiki.apache.org/confluence/display/KAFKA/KIP-72%3A+Allow+putting+a+bound+on+memory+consumed+by+Incoming+requests)
Prior to this implementation, Kafka only support setting upper bbound only on the **number of requests** allowed into the incoming request queue. This is indirectly controls memory consumption but have few drawbacks
- Admin neesd to estimate average request size in order to provide the meaningful size limit
- Size limit must periodically updated if the workload changes and the message size changes
- Server still suspectible to a simultaneous batch of large requests exhausting JVM memory and cause OOM

Third scenario actually happened a few times at LinkedIn - a sudden spike of a very large request batches (1000s requests each) from a Hadoop job caused OOM exceptions on production cluster

The KIP basically allow admin to specify memory limit in **bytes** to resolve the above problems

JMX metrics added to the KIP
 - `MemoryPoolAvgDepletedPercent` - percent of the time request were not being read out of socket due to lack of memory
- `MemoryPoolAvailable` - number of bytes available in the pool
- `MemoryPoolUsed` - number of bytes currently allocated out of the pool and still not returned

## Kafka replication
- [[Kafka replication]]

## Kafka internals
Head over to [[Kafka internals]] for more in depth details

## Kafka transactions
- [[Kafka transactions]]
- [[CFLT - Kafka transactions experiment]]

## Kafka debugging
- [[Troubleshooting Kafka]]
- [[Troubleshooting ZooKeeper]]
- [[Kafka Broker Performance Diagnostics 2.0]]

## Setting up Kafka environment
- [[Setting up Confluent Platform local VM using Multipass]]
- [[Kafka installation and upgrade]]

## Managing Kafka cluster
- [[Monitoring Kafka deployment]]
- [[Expanding and shrinking Kafka cluster]]
- [[Kafka Broker Performance Diagnostics 2.0]]
- [[Monitoring Kafka Performance Metrics]]
- [[Handling broker failure]]

### Shutting down Kafka
Broker process when we perform a clean/controlled shutdown (we send sigterm to process)
- broker then send request to controller
- controller performs leader election
- controller acks brokers
- broker flushes files to disk
- broker shutdown

Performing controlled shutdown can minimize downtime for partition. There will be a brief outage for the clients during leader election

In the event of controlled shutdown, controller only takes a single partition offline at a time. However in an uncontrolled shutdown (crash), **all partitions** which the broker was the leader will go offline at the same time. Given that **controller is only able to elect one leader at a time**, if crashed broker is the leader for 10 partitions, the 10th partition will be offline significantly longer than the first partition

### Gracefully shutting down Kafka
Prerequisite config settings
- All brokers `controlled.shutdown.enable=true`
- Use default for `controlled.shutdown.max.retries` and `controlled.shutdown.retry.backoff.ms`

Process
1. Stop all clients
2. Shutdown one broker at a time
3. Wait for completion; observe log:
	- `..Starting controlled shutdown...`
	- `...Controlled shutdown succeeded...`
	- `...shut down completed...`

## Kafka Multi DC
- [[Multi DC Kafka]]
- [[Cross-DC Replication in Multi DC Kafka Deployment]]
- [[Cross-Zone Consumer Costs in Multi DC Kafka Deployment]]

## Kafka topics
- [[How to delete messages in a Kafka topic]]

## See also
- [[Kafka Streams]]
- [[ksqlDB]]
- [[Confluent Platform]]
- [[Multi DC Kafka]]
- [[MRC]]
- [[Kafka message delivery semantics]]
- [[Kafka exactly once semantics (EOS)]]
- [[Kafka transactions]]
- [[How Kafka zero-copy works]]
- [[Kafka in Production]]
- [[ZooKeeper]]
- [[From Eager to Smarter in Apache Kafka Consumer Rebalances]]

## References
- [Looking into consumer offset topic](https://www.sderosiaux.com/articles/2017/08/07/looking-at-kafka-s-consumers-offsets/#ingest-the-json-into-druid)
- [KIP-72: allow putting a bound on memory consumed by incoming request](https://cwiki.apache.org/confluence/display/KAFKA/KIP-72%3A+Allow+putting+a+bound+on+memory+consumed+by+Incoming+requests)
- [KIP-62: allow consumer to send heartbeats from a background thread](https://cwiki.apache.org/confluence/display/KAFKA/KIP-62%3A+Allow+consumer+to+send+heartbeats+from+a+background+thread) 
- [KIP-500: replace zookeeper with self managed metadata quorum](https://cwiki.apache.org/confluence/display/KAFKA/KIP-500%3A+Replace+ZooKeeper+with+a+Self-Managed+Metadata+Quorum)
- [Kafka 2.8 documentation](https://kafka.apache.org/28/documentation.html)
- [Latest Kafka documentation](https://kafka.apache.org/documentation/)
- [Confluent Platform documentation](https://docs.confluent.io/platform/current/overview.html)
