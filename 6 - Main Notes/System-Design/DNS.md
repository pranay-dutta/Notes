**Topic**: [[System Design]] [[Computer Network]]

DNS (Domain Name System)
----------------------------

DNS is like the phonebook of the internet. It translates human-friendly domain names 
(like www.google.com) into [[IP Address]] (like 142.250.182.196) that computers use 
to identify each other on the network.

[[How DNS works]]

----------------------------
How it works:
----------------------------
1. You type a domain in the browser.
2. The request goes to a DNS resolver.
3. The resolver queries Root, TLD, and Authoritative servers.
4. The IP address is returned, and your browser connects to the site.

----------------------------
Key Components:
----------------------------
- **DNS Resolver**            : Takes your query and starts the lookup.
- **Root Server**               : First step in translating domain names.
- **TLD Server**                 : Handles extensions like .com, .org.
- **Authoritative Server**  : Holds the actual IP info for the domain.

----------------------------
Example:
----------------------------
www.example.com --> DNS --> 93.184.216.34



→ [[System Design]]

