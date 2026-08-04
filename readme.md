# CCNA Packet Tracer Labs 🌐

Daily hands-on practice while studying for the **CCNA (200-301)** certification, following [Jeremy's IT Lab's free CCNA course](https://www.youtube.com/playlist?list=PLxbwE86jKRgMpuZuLBivzlM8s2Dk5lXBQ).

Every day I watch one lecture, complete the matching Packet Tracer lab, and write handwritten notes / flashcards to reinforce the concept. This repo tracks that daily progress.

---

## 📌 Goal

Building a strong networking foundation on the path toward becoming a **Junior SOC Analyst** — CCNA → Security+ → TryHackMe SOC Level 1.

---

## 🗂️ Repo Structure

```
├── Day01-Network-Devices/
├── Day02-Interfaces-and-Cables/
├── Day03-TCPIP-Model/
├── Day04-Cisco-IOS-CLI/
├── Day05-Ethernet-LAN-Switching-Part1/
├── Day06-Ethernet-LAN-Switching-Part2-ARP/
├── Day07-IPv4-Addressing-Part1/
├── Day08-IPv4-Addressing-Part2/
├── Day09-Switch-Interfaces/
├── Day10-IPv4 Header/
├── Day11-Routing-Fundamentals(Part-1)/
├── Day11-Static-Routing(Part-2)/
└── README.md
```

Each folder contains:
- `.pkt` file (Packet Tracer lab)
- Screenshot(s) of the completed topology / CLI output
- Flashcards / notes for that topic

---

## 📅 Progress Log

| Day | Topic | Status |
|-----|-------|--------|
| 1 | Network Devices | ✅ Done |
| 2 | Interfaces and Cables | ✅ Done |
| 3 | TCP/IP Model | ✅ Done |
| 4 | Introduction to Cisco IOS CLI | ✅ Done |
| 5 | Ethernet LAN Switching (Part 1) | ✅ Done |
| 6 | Ethernet LAN Switching (Part 2) – ARP | ✅ Done |
| 7 | IPv4 Addressing (Part 1) | ✅ Done |
| 8 | IPv4 Addressing (Part 2) | ✅ Done |
| 9 | Switch Interfaces | ✅ Done |
| 10 | IPv4 Header | ✅ Done |
| 11 | Routing Fundamentals (Part 1) | ✅ Done |
| 12 | Static Routing (Part 2) | ✅ Done |
| 13 | Subnetting (Part 1) | ✅ Done |

*(Table gets a new row every day — see "How I Update This" below)*

---

## 📖 Daily Breakdown

### Day 1 — Network Devices
Learned about nodes, end hosts/endpoints, and the role of core network devices: routers, switches, firewalls, clients, and servers.
**Lab:** Introduction to Packet Tracer — got familiar with the simulator interface and workspace.

### Day 2 — Interfaces and Cables
Deep dive into cable types and interfaces: Ethernet, UTP, and Fiber Optic.
**Lab:** Connecting devices with the correct cable type:
- Single-mode fiber → long-distance links
- Straight-through → PC-to-switch
- Crossover → switch-to-switch

### Day 3 — TCP/IP Model
Studied each layer of the TCP/IP model in depth — function, operation, protocols, standards, and PDUs (Protocol Data Units) at every layer.
**Lab:** Visualized all 5 layers directly in Packet Tracer (Physical, Local Network, Network, Transport, Application) — first time seeing a packet built/broken down layer by layer.

### Day 4 — Introduction to Cisco IOS CLI
Learned to connect to a Cisco device via console port (rollover cable) and configure it through PuTTY. Covered:
- Running-config vs. startup-config
- Privilege mode & secure passwords
- `service password-encryption` → Type 7 (Cisco proprietary) vs Type 5 (MD5)
- Saving configs: `write`, `write memory`, `copy running-config startup-config`

**Lab:** Console access + password security setup in Packet Tracer.

### Day 5 — Ethernet LAN Switching (Part 1)
Studied the Ethernet frame structure:
- **Header:** Preamble, SFD, Destination MAC, Source MAC, Type
- **Trailer:** FCS (Frame Check Sequence) — 4 bytes, used for error detection
- **MAC Address:** 48-bit (6 bytes), burned into the NIC

### Day 6 — Ethernet LAN Switching (Part 2) – ARP
Learned how ARP (Address Resolution Protocol) resolves IP-to-MAC mappings, and how switches handle traffic:
- **Unknown Unicast → Flood**
- **Known Unicast → Forward**

Also covered minimum Ethernet payload size (46 bytes, padded if smaller) and practiced `ping` while observing ARP resolution in real time.

### Day 7 — IPv4 Addressing (Part 1)
Learned the structure of IPv4 addresses (4 octets, dotted-decimal notation) and how to convert between binary and decimal. Covered IPv4 address classes and subnet masks (netmasks).

### Day 8 — IPv4 Addressing (Part 2)
Learned about the host portion of an IP address: all 0s = Network Address (Network ID), all 1s = Broadcast Address. Learned the formula for maximum usable hosts per network — 2^n − 2 (n = host bits) — and practiced finding the first/last usable IP across Class A, B, and C networks.

**Lab:** Configured R1's hostname, used `show` commands to inspect interfaces, assigned and enabled IP addresses with descriptions, verified via running-config, and saved the configuration. Configured IPs on PC1, PC2, and PC3, then confirmed connectivity via ping between all three.

### Day 9 — Switch Interfaces
Learned to configure interface speed, duplex, and descriptions on a switch. Studied Half Duplex vs Full Duplex (half duplex now legacy, used with hubs) and CSMA/CD (Carrier Sense Multiple Access with Collision Detection) for collision avoidance. Also covered speed/duplex auto-negotiation and interface errors like Runts and Giants.

**Lab:** Configured hostnames on R1, SW1, SW2; assigned IPs to R1, PC1-PC4; manually set speed/duplex on inter-device links; added interface descriptions; disabled unused interfaces.

### Day 10 — IPv4 Header
Deep dive into all 13 fields of the IPv4 header — function and length of each field (Version, Header Length, ToS, Total Length, Identification, Flags, Fragment Offset, TTL, Protocol, Header Checksum, Source/Destination IP, Options). Longest lecture in the course so far. Also examined these fields live in Wireshark on a real captured packet.

### Day 11 — Routing Fundamentals (Part 1)
Learned the two main routing methods — Dynamic and Static (Static covered deeper in Part 2) — and how routing tables work. Covered routing table codes: C (Connected) and L (Local). Configuring an IP address on an interface + `no shutdown` automatically adds both a connected and a local route to the table.

**Lab:** Built a multi-router topology (R1-R4) across several subnets, configured interface IPs on all routers, set up PC1 and PC4 with IPs and default gateways, and verified with `show ip int br`.

### Day 11 — Static Routing (Part 2)
Learned about default gateways and how to configure one, plus static routing theory and configuration.

**Lab 1:** Configured static routes end-to-end (PC1 → SW1 → R1 → R2 → SW2 → PC2) and confirmed bidirectional connectivity via ping.
**Lab 2 (Troubleshooting):** Same topology, but ping was failing. Diagnosed and fixed the root cause — isolating whether it was an IP misconfiguration or a missing/incorrect static route.

**Bonus lab:** Extended the static routing concept into a larger topology — two LANs (SW1, SW2) connected via 4 routers (R1-R4) with two redundant paths (R1→R3→R4 and R1→R2→R4). Configured static routes on all routers and default gateways on all PCs to enable full cross-LAN communication.

### Day 13 — Subnetting (Part 1)
Learned CIDR notation and the fundamentals of subnetting. Practiced finding usable addresses in a Class C network, and worked through dividing 192.168.1.0/24 into 4 subnets sized to accommodate 45 hosts each. Widely considered the hardest CCNA topic — mastery requires heavy practice and comfort with binary-to-decimal conversion.
---

## ✍️ How I Update This README

Each new day, I add:
1. A new row to the **Progress Log** table
2. A new section under **Daily Breakdown** with the topic summary + lab notes
3. A new folder following the naming pattern: `DayXX-Topic-Name/`

---

## 🔗 Connect

Following along daily on https://www.linkedin.com/in/asad-nadeem-72a85b3a5/ (#) — posting progress, labs, and key takeaways from each lecture.