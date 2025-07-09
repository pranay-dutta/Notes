**Topic**: [[System Design]]

<img src="modern-app-architecture.png" width="100%" style="border-radius: 10px; max-width: 380px" />

---
### But how to make communication between de-coupled blocks
> Message queues provide communication and co-ordination for them

🤔[[How message queue works using publishers and consumers]]

---
**Example :-** **Photo customization service**

<img src="photo-customization-service.png" width="100%" style="border-radius: 5px; max-width: 600px" />

- **Independent**
- **Scaled Independently**
- Queue size **large** add more *consumers/workers*
- If Queue is **empty** mostly reduce *consumer/workers*


→ [[System Design]]
