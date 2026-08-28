# Linux and Networking Exercises

Run these in Linux, WSL, or a disposable VM. Adjust package managers and service tools for your distribution. Store evidence, explanations, and screenshots only where helpful in `15-learners/<name>/`.

## 1. Shell, Files, and Permissions

Practice safe navigation and file inspection:

```bash
pwd
ls -la
find . -maxdepth 2 -type f
mkdir -p practice/linux-basics
touch practice/linux-basics/example.txt
chmod 600 practice/linux-basics/example.txt
stat practice/linux-basics/example.txt
```

Deliverable: explain the file's owner, group, and mode. Change its mode back only if you understand the access implication.

## 2. Processes, Signals, and Logs

Start a temporary HTTP server, inspect it, then stop it gracefully:

```bash
python3 -m http.server 8080 > server.log 2>&1 &
ps aux | grep '[h]ttp.server'
ss -ltnp | grep ':8080'
curl -i http://127.0.0.1:8080/
kill -TERM <pid>
tail -n 20 server.log
```

Deliverable: capture the PID, listener address, port, and shutdown result. Use a Go server instead when Module 03 is available.

## 3. Network Identity and Routing

Inspect the host's interfaces, addresses, routes, and DNS configuration:

```bash
ip addr
ip route
resolvectl status
getent hosts github.com
```

If `resolvectl` is unavailable, inspect the distribution's resolver configuration and state that alternative in your notes.

Deliverable: identify the active interface, local address, default gateway, configured resolver, and resolved address for one domain.

## 4. Diagnose a Local Connectivity Failure

Choose or create a service that fails to respond. Use the following sequence instead of guessing:

```bash
ss -ltnp
curl -v http://127.0.0.1:<port>/
curl -v http://<host-address>:<port>/
getent hosts <hostname>
ip route get <address>
```

Deliverable: document one root cause and the evidence that proved it. Examples: no listener, wrong bind address, wrong port, DNS failure, or route failure.

## 5. TCP, UDP, and Packet Path

1. Draw the path of a browser request to a local Go HTTP service.
2. Mark client process, socket, loopback/interface, kernel TCP/IP stack, routing decision, Netfilter point, listening socket, and server process.
3. Explain why a TCP listener is not the same thing as an HTTP handler.

Deliverable: one diagram plus a short explanation of where a firewall rule or reverse proxy would affect the path.

## 6. Optional Advanced: Netlink and Socket Diagnostics

Read the Netlink and source-code references in [RESOURCES.md](RESOURCES.md). In a disposable Linux environment, use `ss` to inspect sockets, then investigate how it obtains kernel information through Netlink and `INET_DIAG`.

Optional deliverable: a minimal Go experiment using [mdlayher/netlink](https://github.com/mdlayher/netlink), with a README that states what it observes and which privileges it needs.

## Self-Assessment

- Can I separate process, port, socket, interface, route, DNS, and firewall failures?
- Can I describe the path of an HTTP request through Linux at a high level?
- Can I safely inspect and stop a local service without using destructive commands?
- Can I explain why Docker, AWS, and Kubernetes require the same networking fundamentals?
