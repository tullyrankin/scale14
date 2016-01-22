# To Shard or Not to Shard?

About Percona

- Solutions for Success with MySQL and MongoDB
- Support, Consulting, Managed Services
- Vendor Neutral: MySQL Percona, MariaDB, RDS
- 100% OpenSource, no lock-in required

First things to decide

- Before you decide how to shard you'd best understand whether or not you really need to shard

Modern Technology

- Can go much further without sharding

Single MySQL Can do

- 10K+ queries per second
- 100K+ rows inserted/updated/deleted per second
- 5M+ rows scanned per second
- 10K+ concurrent connections
- 10TB+ data size

Avoided Sharding

- Enterprise with 200K+ employees Internal Drupal Installation
- E-commerce merchant with $10M+ sales per month

Shareding = Pain

- It is painful! Though you may have gotten used to it.

Sharding Pains

- Developering Complexity
- Operational Complexity
- Technology Complexity
- Complex Failures
- Complex Performance Profile

MySQL Sharding

- Especially painful

Can't Avoid?

- Delay!

Strategies to Delay Sharding

- Architecture
- Functional Partitioning
- Replication 
- Caching
- Queueing

Architecture

- Building up from small blocks
- Each "owning" its data
- "Microservices"

Functional Partitioning

- Keep separate data separate

Replication

- Scale reads
- Beware - they are asynchronous
- Consider Percona ExtraDB Cluster

Caching

- Scale Reads
- Query Cache
- Application Server Cache
- Memcache/Redis
- Summary Tables
- HTTP Cache

Queueing

- Scale Writes
- Balance Demand Spikes
- Batch Work
- Redis
- RabbitMQ
- ActiveMQ
- Kafka

Beyond MySQL

- Analytics
    - Hadoop
    - Vertica
    - Spark
- Full Text Search
    - ElasticSEarch
    - Sphinx
    - Solr
- Document Store
    - MongoDB
    - CouchBase
    - RethinkDB

Optimize!

- Do "simple" optimizations before you decide to shard

Hardware

- Fast CPUs
- Plenty of memory
- Fast flash storage
- Good network (keep it close)

Environment

- Linux is the most common OS
- New MySQL versions scale better
- Use a recent GA version (MySQL 5.7)
- Consider Percona Server and PXC

Configuration

- Configure MySQL Server Properly
    - http://bit.ly/1J8ljaD
- What storage engine is right for you?
    - Consider TokuDB for high compression

Sharding - When?

- Too early
    - Waste resources
- Too late
    - Run into the wall

Architectural Runway

- Sharding is architecture consideration
- Make it part of your architecture runway planning
- How long would it take you to implement Sharding?

Capacity Planning

- Know where your wall is!
- Be conservative in your estimates!
- Do not plan for linear scalability!

Benefits of Sharding

- Yes there are!

Ultimate Scalability

- They only way to scale to "Facebook Scale"

Avoid other complexities

- Complex caching layer
- Asynchronous replication for sharding

Isolation

- Security
- Compliance
- Keeping data close to user

Costs

- Can use lower power systems
- Especially important in the cloud

When to Shard Summary

- Easy in your case
    - Think development and operations
- Scaling up is impossible or too expensive
    - Enterprise? Cloud?
- Your application grow makeing sharding imminent
    - Other optimizations give too short of a runway to care

Sharding Questions

- Sharding "Level"
- Sharding Key(s)
- Sharding Unit
- Sharding HA
- Sharding Technology

Sharding Level

- Database Level?
- "Deployment Unit" Level?

Sharding Key(s)

- Most "small" accesses go to single shard
- No shard is too large in terms of data or load
- May double-store date with different sharding keys if needed

Sharding Unit

- Shard = Physical MySQL Instance
- Shard = Schema
- Multiple "Shards" Per Schema/Table

Sharding HA

- Many Servers = higher chance of failure
- Sharding Increases need for HA
- Sharding over Master-Slave "Clusters"
- Sharding over PXC Clusters

Sharding Technology

- Roll-your-own
- Vitess
- Jetpants
- Shard-Query
- Clustrix
- MySQL Cluster

Sharding Technology

- MySQL Fabric
    - Official solution from MySQL team at Oracle (Open Source)
- Tesora Database Virtualization Engine
    - Automated
    - Open Source
- ScaleArc
    - Rule Based
    - Commercial
- ScaleBase
    - Died

In Summary

- There are multiple technologies for Sharding
- There is no standard solution used across the board

Presenter

- Peter Zaitsev
- pz@percona.com
- @PeterZaitsev
- bit.ly/PerconaJobs
