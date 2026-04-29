# Basic Networking Concepts for DevOps Engineers

Networking is one of the most important skills for a DevOps Engineer because applications, servers, containers, Kubernetes clusters, CI/CD pipelines, monitoring tools, APIs, and cloud services all communicate through networks.

---

# 1. What is Networking?

Networking means connecting computers/devices so they can communicate and share data.

Example:

* Laptop communicates with server
* Browser communicates with website
* Kubernetes pods communicate with each other
* Jenkins communicates with GitHub

---

# 2. IP Address

IP Address = Unique address of a device in a network.

Types:

1. IPv4 → `192.168.1.10`
2. IPv6 → `2001:db8::1`

### Types of IP

| Type       | Example     | Usage                  |
| ---------- | ----------- | ---------------------- |
| Private IP | 192.168.x.x | Internal communication |
| Public IP  | 8.8.8.8     | Internet communication |

### Important Private IP Ranges

| Range                         | Purpose         |
| ----------------------------- | --------------- |
| 10.0.0.0 – 10.255.255.255     | Large networks  |
| 172.16.0.0 – 172.31.255.255   | Medium networks |
| 192.168.0.0 – 192.168.255.255 | Home/office     |

### Commands

```bash
ip addr
ifconfig
hostname -I
```

---

# 3. MAC Address

MAC Address = Physical hardware address of NIC card.

Example:

```bash
00:1A:2B:3C:4D:5E
```

Used inside local network communication.

### Command

```bash
ip link
```

---

# 4. DNS (Domain Name System)

DNS converts domain names into IP addresses.

Example:

```text
google.com → 142.250.183.14
```

Without DNS:

* We must remember IP addresses.

### DNS Flow

```text
Browser → DNS Server → IP Address → Website Opens
```

### Commands

```bash
nslookup google.com
dig google.com
host google.com
```

---

# 5. Port Numbers

Ports identify specific services running on a system.

Example:

```text
IP = House Address
Port = Room Number
```

### Common Ports

| Port  | Service           |
| ----- | ----------------- |
| 20/21 | FTP               |
| 22    | SSH               |
| 23    | Telnet            |
| 25    | SMTP              |
| 53    | DNS               |
| 80    | HTTP              |
| 443   | HTTPS             |
| 3306  | MySQL             |
| 5432  | PostgreSQL        |
| 6379  | Redis             |
| 8080  | Tomcat/Jenkins    |
| 6443  | Kubernetes API    |
| 9090  | Prometheus        |
| 3000  | Grafana/Node apps |

### Commands

```bash
netstat -tulnp
ss -tulnp
lsof -i :80
```

---

# 6. Protocols

Protocols = Rules for communication.

### Important Protocols

| Protocol | Purpose                |
| -------- | ---------------------- |
| HTTP     | Website communication  |
| HTTPS    | Secure HTTP            |
| TCP      | Reliable communication |
| UDP      | Fast communication     |
| SSH      | Remote login           |
| FTP      | File transfer          |
| SMTP     | Email sending          |

---

# 7. TCP vs UDP

| TCP                 | UDP                      |
| ------------------- | ------------------------ |
| Reliable            | Fast                     |
| Connection-oriented | Connectionless           |
| Error checking      | No guarantee             |
| Used in HTTP/HTTPS  | Used in streaming/gaming |

---

# 8. OSI Model

Very important for interviews.

| Layer          | Purpose            |
| -------------- | ------------------ |
| 7 Application  | HTTP, DNS          |
| 6 Presentation | Encryption         |
| 5 Session      | Session management |
| 4 Transport    | TCP/UDP            |
| 3 Network      | IP Routing         |
| 2 Data Link    | MAC Address        |
| 1 Physical     | Cable/Wire         |

### Easy Shortcut

```text
Please Do Not Throw Sausage Pizza Away
```

---

# 9. TCP/IP Model

Real-world networking model.

| Layer          | Protocols |
| -------------- | --------- |
| Application    | HTTP, DNS |
| Transport      | TCP, UDP  |
| Internet       | IP        |
| Network Access | Ethernet  |

---

# 10. Subnetting

Subnetting divides large networks into smaller networks.

Example:

```text
192.168.1.0/24
```

### CIDR Meaning

| CIDR | Hosts         |
| ---- | ------------- |
| /24  | 256           |
| /16  | 65536         |
| /8   | Large network |

### Why Used

* Better security
* Better management
* Reduce traffic

---

# 11. Gateway

Gateway connects one network to another.

Example:

* Local network → Internet

### Command

```bash
ip route
route -n
```

---

# 12. Router

Router forwards packets between networks.

Example:

```text
Home Router connects:
Laptop ↔ Internet
```

---

# 13. Switch

Switch connects devices inside same network.

Works using MAC addresses.

---

# 14. Firewall

Firewall controls incoming/outgoing traffic.

### Linux Firewall

```bash
ufw
iptables
firewalld
```

### Example

Allow SSH:

```bash
ufw allow 22
```

---

# 15. NAT (Network Address Translation)

Converts private IP ↔ public IP.

Example:

```text
Multiple systems use one public IP.
```

Used in:

* Home routers
* Cloud networking
* Kubernetes

---

# 16. DHCP

DHCP automatically assigns IP addresses.

Without DHCP:

* Need manual IP configuration.

### Commands

```bash
dhclient
```

---

# 17. VPN (Virtual Private Network)

Secure encrypted connection between user and company network.

Used in:

* Remote work
* Secure access
* Cloud connectivity

---

# 18. Load Balancer

Distributes traffic across multiple servers.

### Types

| Type    | Usage      |
| ------- | ---------- |
| Layer 4 | TCP/UDP    |
| Layer 7 | HTTP/HTTPS |

### Popular Load Balancers

* NGINX
* HAProxy
* AWS ELB
* Traefik

---

# 19. Reverse Proxy

Client sends request to proxy → proxy forwards to backend.

### Used For

* SSL termination
* Security
* Load balancing
* Routing

### Examples

* NGINX
* Traefik

---

# 20. SSL/TLS

Encrypts communication.

Example:

```text
HTTP  → Not Secure
HTTPS → Secure
```

### Certificate Files

```text
.crt
.key
.pem
```

---

# 21. HTTP Methods

| Method | Purpose    |
| ------ | ---------- |
| GET    | Fetch data |
| POST   | Send data  |
| PUT    | Update     |
| DELETE | Remove     |

---

# 22. API

API allows applications to communicate.

Example:

```text
Frontend ↔ Backend ↔ Database
```

### API Types

* REST API
* SOAP API
* GraphQL

---

# 23. Packet

Packet = Small piece of data transferred over network.

---

# 24. Latency

Latency = Delay in communication.

### Check latency

```bash
ping google.com
```

---

# 25. Bandwidth

Bandwidth = Amount of data transferable.

Example:

```text
100 Mbps
1 Gbps
```

---

# 26. Ping

Checks connectivity.

```bash
ping google.com
```

---

# 27. Traceroute

Shows path packets travel.

```bash
traceroute google.com
tracepath google.com
```

---

# 28. SSH

Remote server access.

```bash
ssh user@server-ip
```

---

# 29. CIDR

CIDR = Compact subnet notation.

Example:

```text
10.0.0.0/16
```

---

# 30. Network Interface Card (NIC)

Hardware/network adapter used for communication.

### Command

```bash
ip link
```

---

# Networking Concepts Important for DevOps Engineers

These are the most important concepts DevOps engineers use daily.

---

# 1. Linux Networking

Must Know:

```bash
ping
curl
wget
netstat
ss
telnet
nc
ip addr
ip route
traceroute
tcpdump
nslookup
dig
```

---

# 2. DNS Troubleshooting

Common Issue:

```text
Website not opening due to DNS failure
```

### Commands

```bash
nslookup
dig
cat /etc/resolv.conf
```

---

# 3. Load Balancing

Used in:

* Kubernetes
* NGINX
* AWS ELB
* Ingress Controllers

Concepts:

* Round Robin
* Sticky Sessions
* Health Checks

---

# 4. Reverse Proxy

Very important in:

* NGINX
* Kubernetes Ingress
* API Gateway

---

# 5. Kubernetes Networking

Very important.

Must Know:

* Pod Networking
* Service Networking
* ClusterIP
* NodePort
* LoadBalancer
* Ingress
* CNI Plugins

### Popular CNI

* Calico
* Flannel
* Cilium

---

# 6. Container Networking

Docker Networking Types:

| Type    | Usage               |
| ------- | ------------------- |
| Bridge  | Default             |
| Host    | Shares host network |
| Overlay | Multi-host          |
| None    | No networking       |

### Commands

```bash
docker network ls
docker inspect
```

---

# 7. Cloud Networking

Important in:

* Amazon Web Services
* Microsoft Azure
* Google Cloud Platform

Must Know:

* VPC
* Subnets
* Security Groups
* NAT Gateway
* Route Tables
* Internet Gateway

---

# 8. Security Groups & Firewall

DevOps engineers manage:

* Open ports
* SSH access
* HTTPS access
* Kubernetes security

---

# 9. SSL/TLS Management

Tasks:

* Renew certificates
* Configure HTTPS
* Troubleshoot SSL errors

Tools:

* Certbot
* OpenSSL

---

# 10. CI/CD Networking

Example:

```text
GitHub → Jenkins → Docker → Kubernetes
```

Need networking between:

* Git server
* CI server
* Registry
* Kubernetes

---

# 11. Monitoring Networking

Tools:

* Prometheus
* Grafana
* ELK Stack

Need:

* Open ports
* Scraping endpoints
* Service discovery

---

# 12. Network Troubleshooting

Daily DevOps Troubleshooting:

| Problem               | Troubleshooting |
| --------------------- | --------------- |
| Server unreachable    | ping            |
| DNS issue             | nslookup/dig    |
| Port blocked          | telnet/nc       |
| Service not listening | netstat/ss      |
| SSL issue             | openssl         |
| Packet issue          | tcpdump         |

---

# 13. API Gateway & Ingress

Used in Kubernetes microservices.

Examples:

* Kong
* NGINX Ingress
* Traefik

---

# 14. Observability Networking

Monitoring tools collect:

* Metrics
* Logs
* Traces

Need proper:

* Port access
* Service discovery
* Scraping configuration

---

# 15. DevOps Networking Architecture Flow

```text
User
 ↓
DNS
 ↓
Load Balancer
 ↓
Reverse Proxy
 ↓
Kubernetes Ingress
 ↓
Service
 ↓
Pod/Application
 ↓
Database
```

---

# Most Important Networking Topics for DevOps Interviews

1. OSI Model
2. TCP/IP
3. DNS
4. HTTP/HTTPS
5. Load Balancer
6. Reverse Proxy
7. Kubernetes Networking
8. Docker Networking
9. VPC & Cloud Networking
10. Firewall & Security Groups
11. SSL/TLS
12. API & API Gateway
13. Troubleshooting Commands
14. Ingress & Service Mesh
15. VPN & NAT

---

# Important Networking Commands for DevOps

```bash
ping
curl
wget
ssh
scp
netstat
ss
ip addr
ip route
traceroute
tracepath
tcpdump
iftop
nmap
dig
nslookup
host
telnet
nc
openssl
```

---

# Real-Time DevOps Networking Issues

| Issue                         | Cause                       |
| ----------------------------- | --------------------------- |
| Pod not reachable             | CNI issue                   |
| 502 Bad Gateway               | Reverse proxy/backend issue |
| SSL handshake failed          | Certificate problem         |
| DNS lookup failed             | DNS issue                   |
| Connection timeout            | Firewall/security group     |
| High latency                  | Network congestion          |
| Jenkins cannot connect GitHub | Port/DNS/proxy issue        |
| Prometheus cannot scrape      | Port blocked                |
