**Topic**: [[System Design]]

📌 Sharding is a **database scaling** technique where a large database is split into smaller, 
 independent pieces called **shards**, each handling a subset of data. Shards can reside on different servers, 
 enabling **horizontal scaling** through data partitioning, unlike replication-based scaling that duplicates entire system.
 

<img src="db-shards.png" width="100%" style="border-radius: 10px; max-width: 500px" />


⭐[[Use of Hash Function in Sharding]]

**Sharded data based on** `userid % 4` 
*( very important to chose a good hash function for even distribution of data )*

<img src="shards.png" width="100%" style="border-radius: 10px; max-width: 400px" />

😟 [[Drawback of Sharding]]

→ [[Database Scaling, Sharding]]