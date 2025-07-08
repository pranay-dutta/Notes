📌**Database Replication** means making a copy of *original database*. 

**DB Replication**
- **Master** - Original DB
- **Slave** - Copy(replica)
<img src="database-replication.png" width=500 style="border-radius: 10px" />


![[database-replication.png]]

| Master                                             | Slave                             |
| -------------------------------------------------- | --------------------------------- |
| Only write operations                              | Read operations                   |
| Insert, Delete, Update *(data-modifying commands)* | Gets *copies of data from master* |
