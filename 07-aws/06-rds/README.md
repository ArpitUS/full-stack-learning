# Module 47: AWS RDS

Run TeamOps PostgreSQL as a managed database with deliberate networking, backup, connection, and recovery decisions. Use the [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html), [RDS for PostgreSQL](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html), and the existing [PostgreSQL connection-management module](../../04-databases/01-postgresql/06-connection-management/).

## Learn

- DB instances, storage, parameter groups, subnet/security groups, backups, snapshots, point-in-time recovery, Multi-AZ, read replicas, encryption, monitoring, and failover.
- Application connection pools, migrations, secret delivery, least-privilege database users, and managed service operational limits.

## Practice Deliverable

Connect TeamOps to a non-public RDS PostgreSQL instance using private network access and safe Go pool settings. Run versioned migrations, verify backup/restore planning, inspect relevant metrics/logs, and document the shutdown/deletion process for the learning instance.

## Completion Criteria

- [ ] Keep the database inaccessible from the public internet.
- [ ] Use application/database credentials through a managed secret/configuration path, not source code.
- [ ] Run migrations repeatably and state the rollback/restore strategy.
- [ ] Explain backups, snapshots, point-in-time recovery, Multi-AZ, and read replicas as distinct capabilities.
- [ ] Configure a bounded Go connection pool and observe database connection behavior.
- [ ] Clean up the test instance and snapshots according to the lab plan.

## Common Mistakes

Public access enabled, security group paths that bypass the application, pooling beyond database capacity, no migration plan, confusing Multi-AZ with read scaling, unreviewed snapshots, and deleting data without verifying retention/recovery requirements.

## Next

Continue to [Module 48: AWS ECS and Fargate](../07-ecs-fargate/).
