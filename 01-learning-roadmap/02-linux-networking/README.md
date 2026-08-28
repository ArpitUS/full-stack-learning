# Module 02: Linux and Networking

Build the Linux and networking foundation needed to run, secure, debug, and operate the Go services built in later modules. This module is based on the [Linux Networking Reading List](https://gist.github.com/eenblam/2e610de9dd089188b354595f10f99823), with a practical full-stack focus.

## Why This Module Comes First

Backend services run as Linux processes, bind to ports, exchange packets, read environment configuration, write logs, and eventually run in containers or cloud networks. Understanding the user-space tools first makes Docker, AWS, Kubernetes, observability, and production debugging easier to reason about.

## Prerequisites

- Complete [Module 01: Git and GitHub](../01-git-github/).
- Use Linux directly, through WSL, a VM, or a disposable cloud instance. Command names and paths may differ on Windows.
- Do not run firewall, routing, traffic-control, or privileged Netlink commands on a shared or production system.

## Learning Path

1. Linux operating basics: shell navigation, files, permissions, processes, signals, environment variables, and logs.
2. User-space networking: interfaces, IP addresses, routes, ports, DNS, TCP/UDP sockets, and HTTP traffic.
3. Service troubleshooting: identify listeners, inspect connections, test name resolution and reachability, read logs, and stop processes gracefully.
4. Packet journey: understand how an incoming packet moves through the network interface, kernel network stack, routing, firewall, socket, and application.
5. Advanced optional study: Netfilter, routing/traffic control, Netlink, socket diagnostics, and programmatic networking with Go.

## Concepts to Understand

- Process versus service; PID, signals, foreground/background jobs, and graceful shutdown.
- Filesystem ownership and permissions; environment variables versus committed configuration.
- Network interfaces, CIDR, default gateways, routing tables, DNS records, ports, and sockets.
- TCP connection lifecycle and the difference between TCP and UDP.
- Listener address semantics: `127.0.0.1`, `0.0.0.0`, private interfaces, and container networking.
- The high-level Linux packet path: NIC -> kernel stack -> routing/Netfilter -> socket -> process.
- Netfilter is kernel packet filtering/NAT infrastructure; Netlink is a kernel-to-user-space messaging interface.

## Practical Artifacts

- A personal Linux service runbook: start, inspect, log, signal, and stop a local Go/HTTP process.
- A network troubleshooting record containing interface, route, DNS, listener, connection, and HTTP evidence.
- A small Go TCP or HTTP service bound intentionally to a local address and port.
- One packet-path diagram from client request to local application process.
- Optional: a Go Netlink or socket-diagnostic experiment in a disposable Linux environment.

## Completion Criteria

- [ ] Find a running service's PID, command, port, and logs.
- [ ] Start and gracefully stop a process using signals.
- [ ] Explain why a service is reachable from localhost but not another machine, or vice versa.
- [ ] Diagnose a failure caused by DNS, routing, firewall, port binding, or an unavailable process.
- [ ] Build and test a small TCP or HTTP listener using Go.
- [ ] Explain the high-level packet journey to the application socket.
- [ ] Record practice evidence and module status in the learner workspace.

## Common Debugging Areas

Binding only to loopback, occupied ports, incorrect firewall/security rules, missing default route, DNS cache confusion, process permission failures, stale environment variables, incorrect file ownership, and assuming a container port is automatically exposed to the host.

## TeamOps Connection

These skills are reused immediately by the Go API modules and later by Docker networking, AWS VPC/security groups, Kubernetes Services/Ingress, observability, DNS, and production-debugging exercises. Keep isolated command notes in the learner workspace; add shared runbooks only when they apply to TeamOps.

## Next Module

Continue to [Module 03: Go Language Fundamentals](../../02-go-backend/01-go-programming/01-language-fundamentals/).
