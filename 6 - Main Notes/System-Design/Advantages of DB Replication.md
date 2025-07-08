**Topic**: [[System Design]]

- **Better performance**
- **Reliability**
- **High Availability**

---
🌍If **Slave DB goes offline** I'll do read requests from **Master DB** and meanwhile I'll ad another new **Slave DB** .
🌍If **Master DB goes offline** meanwhile I'll **promote a Slave to Master DB**

😥 **IRL** systems *promoting* a **slave to master** is very *complicated* because there can be scenarios that **slave** is not **up-to-date**. But there are *recovery scripts* that can work.

→ [[System Design]]