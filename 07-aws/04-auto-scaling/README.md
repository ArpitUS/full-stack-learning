# Module 45: AWS Auto Scaling

Learn to set capacity boundaries from observed demand rather than guesses. Use [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html), [ECS service auto scaling](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html), and [CloudWatch metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html).

## Learn

- Desired/minimum/maximum capacity, target tracking, step/scheduled scaling, cooldowns, health replacement, and multi-AZ behavior.
- CPU, memory, request, queue-depth, and custom metrics; when each can be misleading.
- Capacity protection, scaling limits, cost constraints, and testing scale-in as well as scale-out.

## Practice Deliverable

Define a TeamOps scaling policy using one justified CloudWatch metric. State baseline, target, minimum/maximum capacity, cooldown/scale-in behavior, budget limit, and rollback. Test it only in a controlled environment and capture the observed result.

## Completion Criteria

- [ ] Explain desired, minimum, and maximum capacity.
- [ ] Select a metric connected to actual saturation or user demand.
- [ ] Protect the environment with hard capacity and cost boundaries.
- [ ] Explain scale-out and scale-in risks, including connection draining and cache warm-up.
- [ ] Record the policy, observation, and cleanup result.

## Common Mistakes

No maximum capacity, scaling solely on average CPU, aggressive flapping policies, ignoring startup time, no scale-in design, testing against production, and unbounded spend from a synthetic load test.

## Next

Continue to [Module 46: AWS S3](../05-s3/).
