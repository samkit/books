---
presentation:
    center: false
#   .reveal p {
#     text-align: left;
#   }
#   .reveal ul {
#     display: block;
#   }
#   .reveal ol {
#     display: block;
#   }
---
<!-- slide -->
[TOC]

# CockroachDB
### [Architecture](https://www.cockroachlabs.com/docs/stable/architecture/overview.html)
- https://github.com/cockroachdb/cockroach/blob/master/docs/design.md <font size=30 color=lightgreen>:fa-thumbs-up:</font>
    ![](https://raw.githubusercontent.com/cockroachdb/cockroach/master/docs/media/architecture.png)

- Globally distributed transaction
    - no eventually consistent and staleness issues
- Concepts
    - Cluster
    - Node
    - Range
    - Replica
    - Leaseholder (per range)
- Multi-active availability
- 64MB chunks - 3x replication (sync/async)

#### SQL Layer
- Breaks a SQL query into key-value plan and passes onto transaction layer
- Query is executed closed to data (like hbase)
- DistSql
    - distributed computation when possible

#### Transaction Layer
- Read/Write concurrency - done via MVCC (multi-version concurrency control)

#### Replication Layer
- Node failures result in redistribution of data
- Same for new node addition
- Leaseholder rebalancing - shifts the active lease holder depending on region where traffic is more - so as to avoid n/w latencies
- Raft based consensus for write

##### Storage Layer
- Uses RocksDB for storage
- Time Travel!!!
    - Image what schema versioning can do

### Features
- Multi-active availability
- Simple deployment - container friendly
    - Each node is symmetric so managing deployment is easy
- Strong consistency
    - Due to MVCC, read transaction only looks at data as a snapshot when it started
    - Local/wide area replication
- Dynamic scaling
    - Can be scaled to cloud/additional nodes when under load
    - Entire databases or tables can be moved to even different cloud
- Online schema changes i.e. schema changes without table locks
    - read/write queries are run on cached schema
- Geo-Partitioning!!! - replication can be region aware
    - for eg: ref data can be replicated to different regions for data locality
- Seamless migration from underlying hosts
    - i.e. cross cloud migration can be done without downtime
- Follow-the-workload
- Kubernetes
- [Automated & sophisticated backups](https://www.cockroachlabs.com/docs/stable/backup.html)
    - can be done against AWS S3 (or compatible) and many others
    - supports full/incremental backup
    - backups are also distributed - with data locality

### Notables
- Documentation is good



## Presentation points

<!-- slide -->

# ![CockroachDB](https://portal.cloudclusters.io/media/product_detailed_logo/cockroachdb_kaJLLQh.png)
###### (based on Google Spanner DB)
- [Website](https://www.cockroachlabs.com/)
- [Design doc](https://github.com/cockroachdb/cockroach/blob/master/docs/design.md)
- Google Spanner - https://cloud.google.com/spanner/

<!-- slide -->

### Design Goals
- Symmetric deployment / one binary
- Distributed transactions with strong consistency guarantees
- SQL interface (only) - PostgreSQL compliant
- Horizontal scaling
- Automatic repair & replication (like hdfs)
- Lock-free read and writes (w/ snapshot isolation)
    - reads can continue against cached schema
    - uses MVCC while reading

<!-- slide -->

### Architecture
- Distributed key-value store (not columnar)
- Can handle disk, server/node, datacenter, region failure
- Data is stored in "Ranges" (similar to hdfs blocks)
    - Ranges - RocksDB
    - Range is replicated 3x (default)
    - Range has lease and leaseholder
    - Raft consensus while replicating ranges
- Nodes talk to each other via gossip protocol
```mermaid
graph LR
    Node --> Stores;
    Stores --> Range Replica;
```
- Admin UI with lot of metric


<!-- slide -->
![Architecture](https://raw.githubusercontent.com/cockroachdb/cockroach/master/docs/media/architecture.png)

<!-- slide -->
### Nice/Stand-out Features
- Data Pinning to a region
    - such that data is stored in a particular region but can still be queried from other regions
    - can work at key-level
- Dist-SQL - query computation with data locality
- As-Of queries supported by versioned key-value
    - Older values are garbage collected
- Dynamic scaling - add nodes dynamically and it will manage itself
    - Hardware migration/upgrades with zero downtime (on paper)
    - Can run on cloud - AWS, Google, Azure
- Automatic rebalancing of ranges
- SSL connection
- Backup to S3 (or compliant)
    - snapshot
    - incremental

<!-- slide -->
<!-- slide -->
<!-- slide -->
<!-- slide -->
<!-- slide -->
