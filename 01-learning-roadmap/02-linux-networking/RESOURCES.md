# Linux Networking Resources

The primary inspiration is [eenblam's Linux Networking Reading List](https://gist.github.com/eenblam/2e610de9dd089188b354595f10f99823). Several linked materials are historical; use them for durable concepts and verify commands against current Linux documentation.

## Recommended Order

| Resource | Focus | When to use it |
| --- | --- | --- |
| [Linux Networking Reading List](https://gist.github.com/eenblam/2e610de9dd089188b354595f10f99823) | Packet path, kernel networking, Netfilter, Netlink, source references | Use as the curated map for deeper study. |
| [The Journey of a Packet Through the Linux Network Stack](https://www.cs.dartmouth.edu/~sergey/me/netreads/path-of-packet/Lab9_modified.pdf) | Packet path visualization | Read after basic interfaces, routes, ports, and TCP are familiar. |
| [Linux Kernel Networking](https://www.cs.dartmouth.edu/~sergey/me/netreads/path-of-packet/netLec.pdf) | Kernel networking architecture | Optional deeper study after the packet-path exercise. |
| [Linux Advanced Routing and Traffic Control HOWTO](https://lartc.org/lartc.html) | Routing and traffic control | Reference for advanced routing; use only in disposable labs. |
| [Netfilter](https://www.netfilter.org/) | Firewalling, NAT, and filtering framework | Use alongside firewall/network-policy studies. |
| [`sock_diag(7)`](https://man7.org/linux/man-pages/man7/sock_diag.7.html) | Socket diagnostics through Netlink | Optional after using `ss` in practice. |
| [mdlayher/netlink](https://github.com/mdlayher/netlink) | Go Netlink library | Optional Go exploration after Module 03. |

## Current Documentation Rule

For operational commands, prefer the installed manual pages and current tool documentation:

```bash
man ip
man ss
man systemd
man journalctl
man nft
man tcpdump
```

Record the Linux distribution and command version when a lab result depends on platform behavior.
