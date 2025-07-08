**Topic**: [[System Design]]

1. Data **read** frequently & **modified** infrequently
2. Expiration Policy: 
	- Expiration time *Not to low* - **Data frequently reloaded from DB**
	- Expiration time *Not to high* - **Stale Data**
	
3. **Data** and **Cache** should be consistent

4. **Multiple cache server** across different data centers to avoid **SPOF(Single Point of Failure)**

5.  **Eviction Policy** :- When cache gets full
	- **LRU** *(Least Recently Used)* cache
	- **LFU** *(Least Frequently Used)* cache
	- **FIFO** *(First in First out)* cache

→ [[System Design]]