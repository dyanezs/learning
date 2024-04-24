# Google Professional Data Engineer - Get Certified 2022

This course, taught by Dan Sullivan, covers mostly theory with practical examples for setting up things. He suggests reading the book, docs, and having some hands-on experience with GCP technologies. By taking this course alone won't fully prepare you for the exam.

## Source

- [Udemy](https://globant.udemy.com/course/google-cloud-professional-data-engineer-get-certified/?utm_campaign=email&utm_medium=email&utm_source=sendgrid.com)


## Summary

### Storage
- Object Storage
    - Cloud Storage
- Instance Storage
    - Persisten Disk
- DB Storage
    - SQL
    - NoSQL
    - Analytical DB

#### Cloud Storage
- Unstructured data.
- Archived data.
- Temporary storage among services.
- Global access using URLs.
- Global Namespace | Bucket | Folder | Object
- Clases
    - High Performance: frequent access, Standard. Optimized for performance.
    - Backup and Archival:
        - Nearline: 30 days.
        - Coldline: 90 days.
        - Archive: A year.
- Object Lifecycle Management: We can manage actions like:
    - Move to Archive.
    - Minimum retention.
    - Object holds: Object cannot be deleted or replaced.
- Security
    - Encryption:
        - Google managed.
        - Customer managed: using Cloud Key Management Service.
        - Customer supplied.
- Loading Data
| Small        | Big                                                        |
|--------------|------------------------------------------------------------|
| Console      | Cloud Storage Transfer <br>On Premise transfer: gsutil (< 1TB) <br>Cloud Storage Transfer Service (> 1TB)   |
| Command Line | VPC Network Peering - Between Google Org.                  |
| API          | Cloud VPN - 1.5 Gbps - 3 Gbps                              |
|              | Transfer Appliance - Go to your Data Center 100 TB, 480    |
- Access
    - Uniform Bucket Level Access - IAM.
    - Fine-grained - List of users.
    - Signed URLs - Time limited reads.
    - Signed Policy Documents - e.g. control uploads size and type.

### Relational Databases
- Structured Data.
- Defined Schema.
- ACID Transactions.
- Strong Consistency.
- Normalization.
- Data Structures: Tables, Indexes, Views, Constraints, Partitions.
- Limits
    - 30 TB per Database.
    - Only PostgreSQL, MySQL, SQL Server.
    - Regional Datastore
        - Multiple zones for high availability.
        - Multi-region only for backups.
- Connection
    - Public IP / Private IP.
    - Cloud SQL Auth Proxy: Google runs proxy in Client and Server.

#### Cloud Spanner
- For Relational Databases.
- Multi-regional or global scale.
- Distributed cluster.
- Horizontal scalable 2TB per node.
- Automatic replication between nodes.
- No downtime for maintenance (managed by Google).
- Hot spotting: Some nodes have more workloads.
    - Sequential primary keys (autoincremental).
    - Timestamps: sequential.
    - Alternatives: Hash values or bit reverse or change the order of multiple column index (high cardinality first).
- Interleaved Tables
    - Parent-Child Relationship (one to many).
    - Row from parent table stored with rows from child table.

### Cloud Firestore and Document Databases