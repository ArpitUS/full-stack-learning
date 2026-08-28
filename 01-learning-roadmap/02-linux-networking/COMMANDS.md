# Linux Networking Command Reference

Commands may require Linux, WSL, elevated privileges, or distribution-specific packages. Inspect first; do not modify routes, firewall rules, or traffic control settings on shared systems.

| Goal | Command | What to inspect |
| --- | --- | --- |
| Current directory and files | `pwd`, `ls -la`, `find` | Location, ownership, modes, and files. |
| Process list | `ps aux`, `pgrep -af <name>` | PID, command, and process owner. |
| Process resources | `top`, `htop`, `free -h` | CPU, memory, and process pressure. |
| Send graceful signal | `kill -TERM <pid>` | Process shutdown behavior before using stronger signals. |
| Service logs | `journalctl -u <service>`, `tail -f <file>` | Startup errors, request failures, and shutdown events. |
| Interfaces and addresses | `ip addr` | Interface state and assigned addresses. |
| Routing table | `ip route`, `ip route get <address>` | Default gateway and route selected for a destination. |
| Listening sockets | `ss -ltnp`, `ss -lunp` | Protocol, local address, port, PID, and process. |
| Active connections | `ss -tnp` | TCP state and peer address. |
| DNS lookup | `getent hosts <name>`, `dig <name>` | Resolved addresses and resolver behavior. |
| HTTP diagnosis | `curl -v <url>` | DNS, connection, TLS, request, and response details. |
| Packet capture | `sudo tcpdump -ni <interface> port <port>` | Only in authorized disposable/debug environments. |
| Firewall inspection | `sudo nft list ruleset` | Existing rules; do not change them without a plan. |
| Network namespaces | `ip netns list` | Advanced container/network isolation context. |

## Diagnostic Order

1. Is the application process running?
2. Is it listening on the expected protocol, address, and port?
3. Is the request using the correct host name or IP address?
4. Does DNS resolve to the expected address?
5. Is there a route to that address?
6. Is a firewall, security group, proxy, or network policy blocking it?
7. Do application logs show a request or a failure?

This order keeps troubleshooting evidence-based and maps directly to Docker, AWS, and Kubernetes diagnostics.
