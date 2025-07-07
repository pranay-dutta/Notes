 As we implemented [[Load Balancer]] & **2nd web server**😀 
 
 - 🟢 *No Failover*
 - 🟢 *Improved availability*
 
1. If **server_1** goes offline, **server_2** will get all traffic - *so service won't go offline*
2. Or we can add new healthy web server - *to balance the load*
3. If **website** grows *rapidly* or *servers not enough* to **handle the traffic**
	- We add **one more** server💡, and **load Balancer** will automatically start to **distribute load among them.**

What's next ?
- We still have only one **database** 😨
- What if **DB** goes down.

 😮So we have to use [[Database Replication]]