# Scalability


| Horizontal Scaling | Vertical Scaling |
| ------------------ | ---------------- |
| Load balncing required | N/A |
| Resilient | Single point of failure | 
| Network Calls(RPC) - slow | Inter process communication - fast |
| data inconsistency | Consistent |
| Scales well As users increases | Hardware limit | 


- Taking advantages from both, we make use of a hybrid version which is scaled both horizontally and vertically.
- Intially consider vertical scaling, after reaching a limit. horizontal scaling can only help you to serve more users.
- Ultimately our system need to have these qualities 
    - Resilient (if one goes down, other servers can handle the requests)
    - for a single transaction , prefer Inter Process Communication by scaling a single (or) few set of systems to their maximum level. Thereby we can avoid slow network calls between our servers.
    - The 2nd point can help us with data consistency, for the transactions which are need to be atomic in nature. 


