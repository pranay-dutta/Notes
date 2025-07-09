### 📌Re sharding

- When a shard can *no longer hold* more.
- *Shard exhaustion* due to *uneven distribution* it will require 
*updating sharding function* then move data around.

---
### 📌Celebrity Problem ( Hotspot Key Problem )

- *Sharding* make it *difficult to perform* **JOIN** operations
	- Common fix: **Denormalize** the database so that queries can be done in single table
- *Excessive access* to a particular shard cause *shard overload*

<img src="sharding-celebrity-problem.png" width="100%" style="border-radius: 10px; max-width: 400px" />

- Assign *one celebrity* to *each shard*

<img src="celebrity-shard.png" width="100%" style="border-radius: 10px; max-width: 400px" />

