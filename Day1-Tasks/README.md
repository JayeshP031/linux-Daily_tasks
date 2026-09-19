# Day 1 — Linux Networking & AWS EC2

**Organization:** Fortune Cloud Technologies
**Environment:** Amazon Linux 2023 / AWS EC2
**Date:** 11 September 2026

## 📌 Overview

Day 1 practical tasks focused on Linux networking, IPv4 analysis, AWS EC2 networking, and basic troubleshooting.

## 🧪 Tasks Completed

### 1. Linux IP Investigation

Commands used:

```bash
ip a
ip link
ip route
cat /etc/resolv.conf
hostname -I
```

**Observed configuration:**

| Item         | Result           |
| ------------ | ---------------- |
| Private IPv4 | `172.31.16.110`  |
| Interface    | `ens5`           |
| Network      | `172.31.16.0/20` |
| Gateway      | `172.31.16.1`    |
| DNS          | `172.31.0.2`     |

### 2. IPv4 Analysis

Analyzed the IPv4 address `172.31.16.110` and confirmed it is a **private IPv4 address**.

Connectivity tested using:

```bash
ping -c 4 8.8.8.8
ping -c 4 google.com
```

Both tests were successful.

### 3. Dynamic IP Investigation

Checked dynamic IP configuration using:

```bash
hostname -I
nmcli general status
nmcli device status
```

The `ens5` interface showed a dynamically assigned IPv4 address.

### 4. AWS EC2 Networking

Connected to the EC2 instance using SSH and checked its network configuration:

```bash
hostname -I
ip -4 addr
ip route
curl -4 ifconfig.me
```

The private IPv4 address inside Linux matched the private IP shown in the AWS EC2 Console.

### 5. Network Troubleshooting

Performed basic troubleshooting using:

```bash
ip -4 addr
ip link
ip route
ping -c 4 8.8.8.8
sudo systemctl status nginx
sudo ss -tulpn
curl http://localhost
```

**Results:**

* Network interface → UP
* Default route → Available
* Internet → Working
* Nginx → Running
* Port 80 → Listening
* Local HTTP → Working
* Security Group → HTTP port 80 allowed

## 📸 Evidence

Practical screenshots and detailed evidence are available in:

```text
Day1_Tasks_Submission_Jayesh_Patil.pdf
```

## 🎯 Learning Outcomes

* Linux IP addressing and interfaces
* IPv4 private/public addressing
* Routing, gateway and DNS
* Network connectivity testing
* Dynamic IP concepts
* AWS EC2 networking
* SSH connectivity
* Nginx service troubleshooting
* Ports and AWS Security Groups

## 🔐 Security

Private keys and credentials must never be uploaded to GitHub.

```gitignore
*.pem
*.ppk
.env
.env.*
credentials
.aws/
```

## 👨‍💻 Author

**Jayesh Patil**
