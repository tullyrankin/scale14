Mature Ecosystem

- MySQL: 21 years old -- May 1995
- Percona Server: 7 years old -- November 2008
- MariaDB: 6 years old -- February 2010
- Drizzle: 2008 - 2012 (R.I.P)
- WebScaleSQL: March 2014

History

- 1979: UNIREG
- 1986: UNIREG on UNIX
- mSQL - freely available but not opensource
- 1995: MySQL 1.0 + MySQL AB founded
- 1996: 3.19
- 2000: GPL MySQL Server

History 2

- Shortly thereafter, the dual-license arrives -- libmysql is GPL and not LGPL like before
- May 2000: 3.23.15 - (statement based) replication arrives
- 2001: 3.23 GA
- 2001: InnoDB storage engine (InnoBase Oy)
- 2001: first round VC $$$, Marten Mickos as CEO

History 3

- 2002: MySQL sued Progress NuSphere over the Gemini storage engine
- 2003: VC Series B
- March 2003: 4.0 GA + 4.1 & 5.0 as alpha
- 2003: SAP partnership (hello MaxDB)
- 2003: Acquires Alzato (NDBCLUSTER)

History 4

- October 2004: 4.1 GA (with NDBCLUSTER)
- 2005:5.0 tree is the focus, but it has issues
- October 2005: Oracle acquires Innobase Oy ("InnoDB Friday")
- October 2005: 5.0 becomes GA*
- Late 2005: Maria project starts (make a crash-safe+transactional MyISAM)

History 5

- February 2006: VC Series C
- 2006: Netgrastructure acquired (Falcon engine)
- Pluggable storage architecture - only database that suppot(ed) it
- A "fork" of MySQL Cluster in 2006
- 2006: PBXT (log-based design + performance) ... 2011

History 6

- November 2007: MySQL 6.0 Alpha, 5.1 current tree being worked on but not ready
- 2007: quiet period for IP
- January 2008: Sun Microsystems acquires MySQL AB for USD$1 BILLION
- June 2008: Drizzle - fork of MySQL 6.0 -- modular, fast, microkernel architecture, UTF8, etc.
- November 2008: 5.1GA

History 7

- Late 2008: OurDelta binaries
- November 2008: Percona Server (patchset ~July)
- [http://www.bytebot.net/blog/archives/2009/10/14/clickrs-upgraded-shard](http://www.bytebot.net/blog/archives/2009/10/14/clickrs-upgraded-shard)

History 8

- February 2009: Monty leaves Sun
- March 2009: Final 6.0 Alpha (and shortly dead thereafter)
- April 2009: Oracle acquires Sun Microsystems (January 2010 sale completes, after a long battle with the EU)
    - Shortly thereafter Monty Program Ab is where MariaDB starts being worked on
- October 2009: MariaDB 5.1 Beta release

History 9

- Febryary 2010: MariaDB 5.1 GA release
- November 2010: MariaDB 5.2 GA release
- December 2010: MySQL 5.5 GA
- April 2011: Percona Server 5.5 stable
- February 2012: MariaDB 5.3 GA (GIS, replication, improvements, optimiser)

History 10

- April 2012: MariaDB 5.5 GA
- November 2012: Announcement of MariaDB Foundation
- February 2013: MySQL 5.6 GA
- April 2013: SkySQL Ab acquires Monty Program Ab
- October 2013: Percona Server 5.6 GA

History 11

- March 2014: MariaDB 10 GA
- March 2014: WebScaleSQL -- but there's no GA/shipping release
- October 2015: MariaDB 10.1 GA, MySQL 5.7 GA

Open source community

- MariaDB: takes external contributors/committers
- MySQL: 5.7 takes Generated Columns (virtual columns in MariaDB 5.2) from Andrey Zhakov
    - contributions welcome, commits not
    - see: MySQL Community Contributor Award Program
- WebScaleSQL: Alibaba, Facebook, Google, LinkedIn, and Twitter (w/ Percona + MariaDB also agreeing to work on it)
- Percona: bug reports welcome, commits not

Google Summer of Code

- 2013: 3 contributors (all shipping code, one committer)
- 2014: 4 contributors (all shipping code, a MariaDB Foundation member hired a new developer)
- 2015: accepted with 8 contributors, finally 3 passed

Security

- Oracle: watch for CPUs, or just wait for the next release
- MariaDB: CVEs get fixed quickly when reported
- Percona: roughly follows Oracle, but also takes security from MariaDB
    - http://www.mysqlperformanceblog.com/2013/01/13/cve-2012-4414-in-mysql-5-5-29-and-percona-server-5-5-29/
- For one issue (sql/password.c & memcmp()). MariaDB was first to be patched

Is MySQL dying?

- "The reports of my death have been greatly exaggerated" - Mark Twain
- MySQL ecosystem development is at its **most vibrant now** than it has ever been
- Oracle has been a **great** steward of pushing MySQL development forward

MySQL adoption

- MySQL Server (5.5) still leads the way in Debian/Ubuntu (the only one you can track via popcon)
    - Followed by MariaDB Server and then Percona Server
- Today you can also see stats on the Docker hub, Juju Charms, etc.

But what about he external ecosystem?

- Yahoo! develops monitoring tools
- Yelp opensources replication monitoring
- Box has tools
- Dropbox starts playing around with Fabric
- Booking deploys MaxScale in production
- Pinterest offers up their tools

MySQL 5.7

- Multi-source replication
- Dynamic replication filters
- Lossless sumisync
- SHOW EXPLAIN for connection_id
- GIS functionality
- Statement timeouts
- Change master without stopping SQL thread
- Online GTID impementation
- GTID no longer requires log0slave0-updates to be enabled
- Virtual columns

WebScaleSQL

- Clients can specify millisecond read/write/connect timeouts
- Super read-only to prevent writes by SUPER users
- Prefix index query optimisation
- Idle system flush rate
- Production-ready builds from PSCE

Facebook

- Dynamic columns + indexes? DocStore
- RocksDB, including myrocks_hotbackup
- Asynchronous mysql client support
- max_running_queries / max_waiting_queries
- Relay log writes don't block SHOW SLAVE STATUS

Twitter

- Last updated mid-june 2015 :(
- They made Apache Cotton for Mesos/MySQL

AliSQL

- Further optimised threadpool
- For Single's Day, they have a "hot SKU" fix for inventory deductions of a single SKU
- SQL firewall
- Temporary table space limitations
- Log SHUTDOWN information
- Persistent InnoDB AUTO_INCREMENT (MDEV-6076)
- Column level compression

What about the !server external ecosystem?

- Percona Toolkit
- Percona Extrabackup
- MariaDB MaxScale
- mydumper
- MHA
- etc

(GNU/Linux) Distributions

- Most are defaulted to MariaDB Server 10 (some like RHEL 7 are still on MariaDB Server 5.5)
    - so when you ask for mysql, you effectively get MariaDB Server (beware!)

Where are they now?

- Drizzle - single company opensource project (Rackspace). Most went on to work at OpenStack
- PBXT - PrimeBase focuses on TeamDrive, out of the engine business
- InfoBright
- Calpont InfinDB - to MariaDB Corporation & Oracle
- Tokutek TokuDB - Percona acquires in April 2015

Future?

- MySQL 5.8 is being planned already. Look out for the interesting work behind Cluster & group replication
- Percona Server aims to never become a fork -- work closely with Oracle. Look forward to 5.7
- MariaDB 10.2 will become more of a fork with various features like window functions, CTEs, 5.7 compatibility, etc.
- WebScaleSQL will skip MySQL 5.7; backports to current tree + look at 5.8

Cloud MySQL

- Amazon Web Services Relational Database Service (RDS): MySQL, MariaDB, Aurora
- Rackspace Cloud Databases: MySQL, MariaDB Server, Percona Server
- Google Cloud SQL: MySQL

Discussions

- http://planet.mysql.com
- https://lists.launchpad.net/maria-developers/
- https://lists.launchpad.net/maria-discuss/
- https://groups.google.com/forum/#!forum/percona-discussion

Bugs

- http://bugs.mysql.com
- https://bugs.launchpad.net/percona-server
- https://mariadb.atlassian.net/secure/Dashboard.jspa
- Phabricator https://reviews.facebook.net/

Conferences/Events w/dedicated MySQL track

- SCALE, Los Angeles, CA
- FOSDEM, Brussels, Belgium
- Percona Live Data Performance, Santa Clara, CA
- Oracle OpenWorld, San Francisco, CA

Resources (books)

- High Performance MySQL
- MySQL High Availability

Speaker

- Colin Charles
- colin@mariadb.com
- byte@bytebot.net
- http://bytebot.net/blog
