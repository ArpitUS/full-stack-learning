# Module 44: AWS Load Balancing

Put the TeamOps API behind an Application Load Balancer (ALB) with target health checks and intentional HTTP/TLS routing. Use the [ALB User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) and [target group health checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html).

## Learn

- ALB listeners, listener rules, target groups, health checks, path/host routing, TLS termination, connection draining, and internal versus internet-facing load balancers.
- The distinction between a network connection accepting traffic and an application endpoint being ready to serve it.

## Practice Deliverable

Create an ALB and target group for the disposable EC2 API. Configure a meaningful health path, narrow security-group paths, and document request flow from browser to ALB to target. Add HTTPS only after completing the TLS module or use an explicitly documented temporary lab setup.

## Completion Criteria

- [ ] Explain listener, rule, target group, and health check responsibilities.
- [ ] Route only intended paths/hosts to the application target.
- [ ] Diagnose one unhealthy-target scenario using target health reason and application logs.
- [ ] Explain ALB TLS termination and the traffic boundary behind it.
- [ ] Delete the ALB and target group after the lab when no longer required.

## Common Mistakes

Health endpoint requiring authentication, wrong health-check port/path, ALB/target security-group mismatch, no cross-AZ plan, treating an ALB as application authorization, forgotten ALBs, and relying on sticky sessions to hide stateful design problems.

## Next

Continue to [Module 45: AWS Auto Scaling](../04-auto-scaling/).
