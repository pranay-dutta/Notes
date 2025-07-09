**Topic**: [[System Design]]

- **Small Website** - Few servers - *Not a necessity*
- **Busy & popular website** - *Essential*

---
**● Logging : -**
- Monitoring error logs
- Per server level
- Centralized logging : New Relic, Sentry

---
**● Metrics : -**
- Gain business insights 
- Aware of health of our service

 1. **Host level metrices :** CPU, Memory, etc. 
	 - **Example**: *Grafana*
 2. **Aggregated Level metrices :** Performance of DB, Cache, etc.
 3. **Key Business metrices :** Daily active users, revenue, etc.

---
**● Automation : -**
- When system gets big & complex
- Automation tools
- Improve productivity

1. **Continuous Integration**
	- Code check-in verified through automation 
2. Automating builds, test deployment etc.

→ [[System Design]]