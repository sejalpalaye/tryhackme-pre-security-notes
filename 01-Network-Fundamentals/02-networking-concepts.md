# Networking Concepts

## OSI Model
A framework that explains how data travels across a network in 7 layers.

| Layer | Name | What it does |
|-------|------|--------------|
| 7 | Application | User-facing apps (HTTP, FTP, DNS) |
| 6 | Presentation | Data formatting, encryption, compression |
| 5 | Session | Opens, manages, closes sessions |
| 4 | Transport | Reliable delivery, error checking (TCP/UDP) |
| 3 | Network | IP addressing and routing |
| 2 | Data Link | MAC addressing, frames |
| 1 | Physical | Actual cables, signals, hardware |

> Easy way to remember (top to bottom): **All People Seem To Need Data Processing**

---

## TCP/IP Model
A simplified 4-layer version of OSI used in real-world networking.

| TCP/IP Layer | Equivalent OSI Layers |
|-------------|----------------------|
| Application | Layers 5, 6, 7 |
| Transport | Layer 4 |
| Internet | Layer 3 |
| Network Access | Layers 1, 2 |

---

## IP Addresses & Subnetting

- Every device on a network needs a unique IP
- Subnetting divides a network into smaller sub-networks
- Subnet mask tells us which part is the network and which is the device

| Term | Example |
|------|---------|
| IP Address | 192.168.1.10 |
| Subnet Mask | 255.255.255.0 |
| CIDR Notation | 192.168.1.0/24 |

---

## UDP vs TCP

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-based | Connectionless |
| Reliability | Reliable | Unreliable |
| Speed | Slower | Faster |
| Use case | Web, email, file transfer | Streaming, gaming, DNS |

---

## 3-Way Handshake
How TCP establishes a connection between two devices.

```
Client → SYN      → Server   (I want to connect)
Client ← SYN-ACK  ← Server   (Okay, I acknowledge)
Client → ACK      → Server   (Connection established)
```

---

## Encapsulation
The process of wrapping data with headers as it moves down the OSI layers.

- Each layer adds its own header (and sometimes trailer)
- At the receiving end, each layer removes its header (decapsulation)

```
Data → Segment → Packet → Frame → Bits
```

---

## Telnet vs SSH

| Feature | Telnet | SSH |
|---------|--------|-----|
| Encryption | No | Yes |
| Security | Insecure | Secure |
| Port | 23 | 22 |
| Use today | Rarely used | Standard for remote access |

```bash
# Connect via SSH
ssh username@192.168.1.1

# Connect via Telnet (insecure)
telnet 192.168.1.1
```
