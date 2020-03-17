# Apache-Kafka
Apache Kafka
publish/subscribe

messaging pattern

sender(publisher) -> receiver(subscriber)


Metrics 
Users 

Broker 

Bulletin Board 

Open-source pub/sub msg system 
Distributed Event Log 
Immutable 

Persisted on disk 
(retention policy) Main Difference

Hybrid btw msg system and db 

Reliable and high-throughput platform

real-time data streams data pipelines 
single place for storing and distributing events 

integration complexity  

ETL(Extract, Transform, Load)

CDC(Change Data Capture)
Big Data Ingest 


Kafka Architecture 

Cluster (at least three broker to provide redundancy)
Producer ->  Assigning offsets; committing messages to Disk 
Consumer -> Fetch request & serve msgs 


Topics categorize  partition 
commit log guarantees ordering 
easy scaling 
high throughput 

central hub 

---------------------------------------------
Messages 

Single unit of data 
just a byte array 
optional key 


User A 
User ID % # of partitions assign the same partition for user 
Topic 

No Ordering Guarantee 
Round-robin by default 


Batches 
trade-off Latency VS Throughput 
can be compressed 

Schemas 
- JSON 
- XML
- AVRO
- PROTOBUF

Ordering = One partition 

Each partition can be in many servers 
horizontal scale


easy to stop/restart 

Consumer Groups

Group A 
Topic 

Consumer Horizontal Scaling 
Rebalance

- consumer belong to different consumer groups 


thousands of partitions and millions of msgs per second 

cluster of brokers 
one broker act as cluster controller:
	assign partitions 
	monitoring for broker failures 

Leader of partition 

Retention 
Durable storage of messages 
Time(7 days default) Size(EG 1GB)
oldest messages are expired & deleted 
min amount of data available at any time 


Reliability Guarantees 
Behaviours that should be preserved 

consumer will read A -> B
Msgs are "committed" when written to the leader and all in-sync replicas 
committed msgs won't be lost 
one replica remains alive
retention policy holds 

consumers can only read committed msgs
kafka provides at-least-once msg delivery semantics
 
no exactly-once semantics

external systems

kafka streams 
trade-offs 
reliability
consistency         
vs
Availability
High Throughput
Low latency
----------------------------------------------------         

Pros
- tackles integration complexity 
- ETL/CDC 
- Big Data Ingestion
- High throughput 
- Disk-based retention
- Multiple Producers / Consumers
- Highly Scalable
- Fault Tolerant
- Fairly Low-Latency
- highly configurable
- Provides backpressure


Cons
- requires a lot of time to understand and don't shoot yourself in the foot
- Not the best solution for real low-latency systems 

----------------------------------------------------      
JMS (Java Message Service)

Consumers pull msgs from brokers RETENTION
Easy to replay msgs
Ordering within partition
Easy to build
Ordering within partition
scalable and fault tolerant systems 

Msges pushed to consumer Hard to achieve backpressure 


Frameworks 
Kafka Stream/Connect 

The Definitive Guide 
 




