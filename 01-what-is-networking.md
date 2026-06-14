# What is Networking?

## Definition
A network is a group of devices connected together to communicate and share resources.

## What is an IP Address?
A unique identifier assigned to every device on a network.

| Type | Format | Example |
|------|--------|---------|
| IPv4 | 32-bit, 4 octets | 192.168.1.1 |
| IPv6 | 128-bit | 2001:0db8::7334 |
| Public IP | Visible on internet | Assigned by ISP |
| Private IP | Within local network | 192.168.x.x |

## What is a MAC Address?
A hardware identifier assigned to a device's network card (NIC).

- Format: `00:1A:2B:3C:4D:5E`
- First 3 pairs = manufacturer
- Last 3 pairs = unique device ID
- Works at Layer 2 (Data Link Layer)

## MAC Spoofing
Changing your MAC address to impersonate another device.

- Used to bypass MAC filtering on networks
- Only changes the software-level MAC, not the hardware

```bash
# View MAC address
ip link show

# Change MAC address temporarily
sudo ip link set dev eth0 down
sudo ip link set dev eth0 address 00:11:22:33:44:55
sudo ip link set dev eth0 up
```

## Ping / ICMP
Ping tests connectivity between two devices using ICMP protocol.

- Sends ICMP Echo Request → receives ICMP Echo Reply
- Measures round-trip time (RTT) in milliseconds
- Firewalls often block ICMP to hide live hosts

```bash
ping google.com
ping -c 4 192.168.1.1
```
