# Module 42: AWS Fundamentals

Build the security and network model for a non-production TeamOps environment. Use the [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html), [IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), and [VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html).

## Learn

- Accounts, Regions, Availability Zones, shared responsibility, billing boundaries, and service quotas.
- IAM users, roles, policies, trust policies, least privilege, MFA, and temporary credentials.
- VPCs, public/private subnets, route tables, internet/NAT gateways, security groups, network ACLs, DNS, and CloudWatch.

## Practice Deliverable

Create a diagram for a least-privilege TeamOps learning environment: VPC, public ALB subnet(s), private application/database subnet(s), route boundaries, security groups, IAM roles, logging, and resource tags. Define budget/teardown controls before provisioning.

## Completion Criteria

- [ ] Explain Region versus Availability Zone and public versus private subnet.
- [ ] Write a least-privilege policy/trust relationship for one workload role.
- [ ] Explain security groups versus network ACLs and stateful versus stateless filtering.
- [ ] Identify inbound/outbound paths for browser, ALB, API, database, and S3 traffic.
- [ ] Define tags, budget alarm, and resource cleanup ownership.

## Common Mistakes

Long-lived access keys, overly broad policies, public databases, security groups open to all traffic, confusing route tables with firewalls, ignored costs, and untagged resources that cannot be traced or removed.

## Next

Continue to [Module 43: AWS EC2](../02-ec2/).
