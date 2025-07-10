**Topic**: [[System Design]] #editpending #horizontalscalingisnotsharding 

Horizontal scaling and sharding are related concepts, but they are not exactly the same thing. 

Horizontal Scaling: Horizontal scaling refers to the process of adding more machines or nodes to a system to increase its capacity and performance.
This is often done by distributing the workload across multiple machines. In horizontal scaling, each new machine added to the system is a 
replica of the existing machines, and they collectively handle the increased load. 
Horizontal scaling is a general term that can be applied to various architectures and systems. 


Sharding: Sharding is a specific database design and scaling technique where a large database is partitioned into smaller, more manageable pieces called shards. Each shard is a self-contained database, and different shards can be located on different servers or clusters. Each shard handles a subset of the overall data. Sharding is a type of horizontal scaling, but it specifically involves partitioning the data, while other forms of horizontal scaling may involve duplicating the entire system without necessarily partitioning the data.
## 📌Also known as scale-out

Large DB gets sharded into small shards 

<img src="db-shards.png" width="100%" style="border-radius: 10px; max-width: 500px" />

---

Adding more servers in case of **DB** called sharding
> Example: bought more servers

→ [[System Design]]