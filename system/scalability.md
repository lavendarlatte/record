## Scalability

### Vertical scaling
More RAM, SSD, CPU - has physical limit.

### Horizontal scaling
Multiple cheaper servers. Public IP address should point to **load balancer** and use private IP addresses for servers. We cannot load balance in DNS server level because clients usually cache DNS record (TTL: time to live), and subsequent requests will go to the same server.

Using multiple server can mean now session is broken, so we can think of having a separate server for shared state. Then, there is no redundancy, and uptime is bad if this file server breaks.

Redundancy in one server can be achieved by RAID.
* RAID 0: striping without fault tolerance. One stripe can be accessed together.
* RAID 1: mirroring whole disk.
* RAID 5: block level striping, N+1 parity disk.
* RAID 6: block level striping, N+2 parity disk.