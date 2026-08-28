# Module 43: AWS EC2

Deploy a containerized TeamOps API on a controlled virtual machine to learn host-level deployment and operation. Use the [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) and [EC2 security best practices](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security.html).

## Learn

- Instance types, AMIs, key pairs, instance roles, user data, metadata, security groups, EBS, snapshots, monitoring, and lifecycle.
- SSH access versus Systems Manager-style managed access, patching responsibility, host logs, and instance replacement.

## Practice Deliverable

Deploy the Module 37 Dockerized API to a disposable EC2 instance. Use an IAM role rather than embedded credentials, narrow inbound rules, a health endpoint, documented configuration, logs, and a documented terminate/cleanup path.

## Completion Criteria

- [ ] Explain AMI, instance, EBS volume, security group, IAM role, and user data roles.
- [ ] Reach the service only through intentionally allowed network paths.
- [ ] Use least-privilege workload credentials and avoid storing keys on the instance.
- [ ] Capture logs/health evidence and document recovery by replacing rather than manually repairing an instance.
- [ ] Terminate the learning instance and confirm dependent resource cleanup.

## Common Mistakes

Public SSH to the world, reused personal keys, credentials in user data, manually configured snowflake hosts, unpatched images, unattached EBS volumes, unused Elastic IPs, and forgotten running instances.

## Next

Continue to [Module 44: AWS Load Balancing](../03-load-balancing/).
