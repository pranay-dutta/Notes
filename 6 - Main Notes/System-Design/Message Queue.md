**Topic**: [[System Design]]

<img src="modern-app-architecture.png" width="100%" style="border-radius: 10px; max-width: 380px" />
### But how to make communication between de-coupled blocks
> Message queues provide communication and co-ordination for them

[[How message queue works using publishers and consumers]]
**Message queue**
- Support *Asynchronous communication*

<img src="message-queue.png" width="100%" style="border-radius: 10px; max-width: 600px" />

⭐ **Producer (publisher)** can produce a message to queue even when *consumer is unavailable.*
⭐ **Consumer (subscriber)** can read from queue even when *producer is unavailable*.

**Example :-** **Photo customization service**


→ [[System Design]]
