Date: [[2021-02-08]]
Goal: Figure out Globex latency problem on the consumer code

---

## [[2021-02-02]]
- Background on latency
- Last few days, delay on producer to consumer
	- Producer log acknowledgement is fast
	- Issue on consumer side ~500ms later
	- Latency growing overtime but if you restart component latency goes down and starts growing again
- Questions raised
	- Share the topology, pipeline
	- Are you collecting thread id (on consumer)
	- How do you collect the data
	- Consumer code
	- Clocks on producers and consumers synchronised. Could be NTP drift
		- Clocks are in sync, latency is measurable
- Consumer code
	- Spring Boot app, uses camel route
	- Kafka endpoint
		- Within endpoint — set config
		- Camel handles all routing
		- `setFetchWaitMaxMs` = 50
			- Should be higher value, lower value increases network traffic
			- Should be around 500ms
		- `setMaxPollRecords` = default value = 1
		- `setConsumersCount` = 10 in production
	- Likely synchronous consumer processing — not delegated to thread pool
	- Would be good to have log entry at the end of data processing
	- `endpoint_direct_rpc_call` runs within the same thread
		- direct rpc call is multithreaded through SEDA
		- `blockWhenFull=true` — may accumulate 100 messages in blocking queue for SEDA
- Summary of recommendations
	- Add log entry right after `end_direct_rpc_call` to see when ready to process next message
	- Log entry should contain thread id
	- Collect statistics, not just single latency call, to see how it changes over time
	- Instrument consumer application with JMX exporter + Prometheus
		- Latency between producer timestamp and when message is consumed
		- Most important: time between subsequent polls
	- Consumer has timestamp on the message — use it
	- Check what Camel exposes on the endpoint — SEDA queue size is useful
- Poll record split by partitions; if set to 1 then at most 1 or 0
