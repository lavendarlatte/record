## Scalability

### Vertical scaling
More RAM, SSD, CPU - has physical limit. No redundancy.

### Horizontal scaling
Multiple cheaper servers. Public IP address should point to **load balancer** and use private IP addresses for servers. We cannot load balance in DNS server level because clients usually cache DNS record (TTL: time to live), and subsequent requests will go to the same server. LB can save random number to server IP mapping instead and set random number to cookie saved in user browser to maintain session for a certain amount of time.

* We need to make sure all servers are running the same application, and they should not save user data in local memory. 

Now sessions need to be stored in a centralized data store which is accessible to all servers. Then, there is no redundancy, and uptime is bad if this file server breaks. 

### Database replication

Redundancy in one server can be achieved by RAID.
* RAID 0: striping without fault tolerance. One stripe can be accessed together.
* RAID 1: mirroring whole disk.
* RAID 5: block level striping, N+1 parity disk.
* RAID 6: block level striping, N+2 parity disk.

Still, server can lose power so we need replication.
* Master-Slave: multiple slaves copy one master, gives redundancy = reliability and also good for read-heavy application. Write is only done in master. When one slave is offline other slave will handle the requests. When master is offline, slave will be promoted and there will be data recovery process after.
* Master-Master: multiple masters.

### Database partitioning

### Relational vs Non-relational DB
* Relational: RDBMS/SQL, MySQL, Oracle database, PostgreSQL, etc. Relational databases represent and store data in tables and rows. You can perform join operations using SQL across different database tables.
* Non-relational: NoSQL, CouchDB, Neo4j, Cassandra, HBase, Amazon DynamoDB, etc. These databases are grouped into
four categories: key-value stores, graph stores, column stores, and document stores. Join operations are generally not supported in non-relational databases.

MySQL is more common, but if your application requires super-low latency, your data are unstructured, you need to store a massive amount of data, and you only need to serialize/deserialize data, consider NoSQL.

### Caching
* HTML: saving HTML pages can help with compute time, but it requires more space and it is hard to update after.
* MySQL query cache: if the same query comes again return results right away.
* memcached: in-memory.