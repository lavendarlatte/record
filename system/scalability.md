## Scalability

### Vertical scaling
More RAM, SSD, CPU - has physical limit.

### Horizontal scaling
Multiple cheaper servers. Public IP address should point to **load balancer** and use private IP addresses for servers. We cannot load balance in DNS server level because clients usually cache DNS record (TTL: time to live), and subsequent requests will go to the same server.

Using multiple server can mean now session is broken, so we can think of having a separate server for shared state. Then, there is no redundancy, and uptime is bad if this file server breaks.