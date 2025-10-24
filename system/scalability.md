## Scalability

### Vertical scaling
More RAM, SSD, CPU - has physical limit.

### Horizontal scaling
Multiple cheaper servers. Public IP address should point to **load balancer** and use private IP addresses for servers. We cannot load balance in DNS server level because clients usually cache DNS record (TTL: time to live), and subsequent requests will go to the same server. LB can save random number to server IP mapping instead and set random number to cookie saved in user browser to maintain session for a certain amount of time.

* We need to make sure all servers are running the same application, and they should not save user data in local memory. 

Now sessions need to be stored in a centralized data store which is accessible to all servers. Then, there is no redundancy, and uptime is bad if this file server breaks. 

Redundancy in one server can be achieved by RAID.
* RAID 0: striping without fault tolerance. One stripe can be accessed together.
* RAID 1: mirroring whole disk.
* RAID 5: block level striping, N+1 parity disk.
* RAID 6: block level striping, N+2 parity disk.

Still, server can lose power so we need replication.
* Master-Slave: multiple slaves copy one master, gives redundancy and also good for read-heavy application.
* Master-Master: multiple masters.

MySQL vs NoSQL
denormalize right from the beginning and include no more Joins in any database query. 