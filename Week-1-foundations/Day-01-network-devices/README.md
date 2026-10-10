# Day 01 — Network Devices

**Jeremy's IT Lab:** Day 01 | **Topic:** N10-009 Obj 1.1 — Network Devices
**Difficulty:** ⭐ Easy 

---

## 🎯 Objective
Identify and place the correct network devices (router, switch, hub, PC, server) in Packet Tracer and understand what each one does at which OSI layer.



## 📋 Devices Used

| Device | OSI Layer | Function |
|---|---|---|
| Hub | Layer 1 | Broadcasts to all ports — obsolete |
| Switch (Layer 2) | Layer 2 | Forwards frames by MAC address |
| Multilayer switch | Layer 2 + 3 | Switches by MAC **and** routes by IP (SVIs, routed ports) |
| Router | Layer 3 | Routes packets by IP address |
| PC | Layer 3–7 | End device |
| Server | Layer 3–7 | Hosts services (DNS, DHCP, web) |

## 🔑 Which devices need an IP address?

| Device | IP address needed? | Why |
|---|---|---|
| Hub | No | Layer 1, just repeats bits |
| Layer 2 switch | **Not to forward traffic** | Forwards by MAC. An IP is only for **management** (Telnet/SSH) on a VLAN interface, plus a default gateway to be reachable from other subnets |
| Router | Yes, on every interface in use | Each interface is the gateway of its subnet |
| Multilayer switch | Yes, on SVIs and routed ports | It routes, so it has Layer 3 interfaces (see Day 06) |
| PC / server | Yes (IP, mask **and** default gateway) | End hosts |

## ✅ What I Verified
- Each device is correctly placed in the topology
- I can identify each device's OSI layer
- I understand the difference between a hub and a switch
- I know when a switch needs an IP address (management only)

## 💡 What I Learned
- A Layer 2 switch forwards by MAC address and needs **no IP** to switch traffic. In my labs the PCs and router interfaces had IPs, the switches didn't.
- A switch can still take an IP for management: `interface vlan 1` + `ip address ...` + `ip default-gateway ...`.
- A **multilayer switch** can route. That is what let me replace the router's job with SVIs in Day 06.


## 📎 Files
- `network-devices.pkt` — Packet Tracer file

---
*Source: Jeremy's IT Lab Day 01 | N10-009 Obj 1.1*
