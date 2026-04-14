# Lab 02 — Multi-Switch + Firewall Security

**Status:** In Progress  
**Tool:** Cisco Packet Tracer 9.0  
**Builds on:** [Lab 01 — VLAN Segmentation + Router-on-a-Stick](../lab-01-vlan-roas/)

---

## Objective

Extend the Lab 01 network to address three real-world gaps: single point of failure on the switch, no external access simulation, and no security boundary between internal departments and outside traffic.

---

## What's Being Added

### 1. Second Switch (Redundancy + Collision Reduction)
Lab 01 runs everything through one switch. A single hardware failure takes down all 8 devices and all 4 departments simultaneously — that's not acceptable in any real environment.

Adding a second switch allows traffic to be distributed across two physical devices. Spanning Tree Protocol (STP) prevents loops between the two switches while still providing a failover path if one goes down. Departments can be split across switches so a single failure only impacts part of the network, not all of it.

### 2. External Router (Simulated Outside Vendor)
Lab 01 has no representation of anything outside the internal network. In a real office, vendors, remote workers, or partner organizations need to reach specific internal resources — not the entire network.

A second router simulates this external connection. It represents a theoretical outside source (vendor, ISP hand-off, remote office) attempting to reach internal departments.

### 3. Firewall (Security Boundary)
Without a firewall, the external router can reach anything on the internal network. That's the problem. A firewall — placed between the external router and the internal network — enforces which traffic is allowed in, from where, and to what destination.

This introduces:
- **Zones:** Outside (untrusted), DMZ (semi-trusted), Inside (trusted)
- **ACL policy:** Explicit permit/deny rules controlling what crosses each boundary
- **Stateful inspection:** Return traffic is permitted automatically; unsolicited inbound is dropped

---

## Planned Topology

```
[Outside Router]  ←— simulates external vendor / internet hand-off
       |
   [Firewall]     ←— enforces zone policy (outside / inside)
       |
  [Core Switch 1] ←— existing switch from Lab 01
       |
  [Access Switch 2] ←— new switch, connected via trunk
  /    |    \
[IT] [Sales] [Accounting] [HR]
```

---

## Skills This Lab Covers

- Layer 2 redundancy with dual switches and STP
- Inter-switch trunking
- Firewall zone configuration (outside / inside)
- Basic ACL security policy
- Simulated external access to internal resources

---

*Documentation will be completed as the lab is built.*
