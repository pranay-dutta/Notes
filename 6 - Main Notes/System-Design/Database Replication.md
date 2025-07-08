📌**Database Replication** means making a copy of *original database*. 

**DB Replication**
- **Master** - Original DB
- **Slave** - Copy(replica)

| Master                                             | Slave                             |
| -------------------------------------------------- | --------------------------------- |
| Only write operations                              | Read operations                   |
| Insert, Delete, Update *(data-modifying commands)* | Gets *copies of data from master* |

<img src="database-replication.png" width=400 style="border-radius: 10px" />

---

😮**Most applications** = (**read** to **write** ratio) **read requests** are much usually higher
That's why  *Number of slaves* > *Masters*

[[Advantages of DB Replication]]

→ [[System Design]]