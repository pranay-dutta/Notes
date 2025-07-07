 📌Based on previous design [[Scaling of server]]
 - Users *connected directly*
 - What if server *goes offline*😮
 - Also, when **many users** access at the *same time*
	 - Web Server *load limit*
	 - Slow response
	 - Fail to connect

☹️ We can't use Load Balancer for [[Vertical Scaling]]. Because we are **not increasing the server** count we are **increasing it's power** only.

> Load Balancer 🗿
- **Evenly distributes** web traffic
- Users **connect** to **Load Balancer** via **Public IP**
- **Load Balancer** communicate with **web servers** via **Private IP**
