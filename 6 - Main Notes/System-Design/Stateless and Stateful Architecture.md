**Topic**: [[System Design]]

📌Session Data / State :- Data that represents user's session on web.
- *identify a user*
- *Authenticate the user*

<img src="webserver-user-A-user-B.png" width="100%" style="border-radius: 10px; max-width: 400px" />

### But this is a problem
- User **A's** request will have to be **redirected** to **Server 1** only😟 *(possible using sticky session: in load balancer)*
- In this case **Stateless architecture** will help us 💪

<img src="multiple-user-server-diagram.png" width="100%" style="border-radius: 10px; max-width: 500px" />

[[Comparison between Stateful and Stateless architecture]]

→ [[System Design]]