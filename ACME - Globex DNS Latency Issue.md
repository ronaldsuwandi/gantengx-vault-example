A customer encountered a problem with 5 second delays from time to time. The delay was **precisely 5 seconds**. Investigation found this was a DNS issue.

In Linux, if there is [[5 seconds delay latency is typically due to DNS|a 5 second constant or multiple of 5 seconds timeout, it's likely DNS]]

- Producer thread
	- Network thread opens connections
	- IO handling async
	- epoll
		- 1 thread for read and write
		- Thread registers interest in operations
		- When resource is ready, schedule the IO
	- In Java all traffic goes through async IO
		- Except for name resolution
		- `kafka/clients/ClientUtils.java` line 62
	- If you have both IPv4 and IPv6 in a stack, DNS queries execute in parallel using both — typically in UDP
	- Before establishing connection
		- Need to get IP
		- In this case, some component simply dropped the IPv4 query — on retry it worked properly
- DNS tcpdump findings
	- DNS for both A (IPv4) and AAAA (IPv6)
	- AAAA gets an immediate answer
	- 5 seconds later, retry on A
		- After retry: A = no such name
		- Another retry: A responds
	- Fix: don't send A and AAAA in parallel — send them serially
