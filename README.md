# RTS OF OSPF SIMULATION USING CISCO PACKET TRACER

## Real-Time Inter-Campus Research Collaboration Network Using OSPF

### Author
**Aravinth N**  
B.E. Electronics and Communication Engineering  
Saveetha Engineering College

---

# Abstract

Open Shortest Path First (OSPF) is a dynamic routing protocol used to exchange routing information between routers automatically. It enables routers to discover the shortest path and maintain efficient communication across multiple networks.

This project demonstrates the implementation of OSPF using Cisco Packet Tracer through a real-time inter-campus research collaboration network. The simulation illustrates OSPF neighbor formation, route exchange, route calculation, and packet forwarding between two research laboratories located in different campus blocks.

---

# Introduction

Modern educational institutions and research organizations require reliable communication between geographically separated departments. As network size increases, manual routing becomes difficult to manage.

OSPF solves this problem by automatically discovering routes and selecting the best path for packet transmission.

This project simulates two research laboratories connected through OSPF-enabled routers.

---

# Real-Time Scenario

Saveetha Engineering College has established two advanced research laboratories working together on a national-level project.

## Project Name

### Smart Autonomous Traffic Monitoring System

The research teams continuously exchange:

- Research papers
- Simulation outputs
- Sensor datasets
- Project reports
- Technical documentation

Since the laboratories are located in different campus blocks, OSPF is implemented to enable automatic route discovery and seamless communication.

---

# Campus A – AI & Embedded Systems Research Lab

### Researchers

- Aravinth N (PC0)
- Vignesh Kumar (PC1)

### Network Components

- Switch0
- Router2

### Network

```text
192.168.0.0/24
```

### Gateway

```text
192.168.0.200
```

---

# Campus B – Communication Networks Research Lab

### Researchers

- Maadeash K (PC2)
- Karthik Raj (PC3)

### Network Components

- Switch1
- Router5

### Network

```text
192.168.1.0/24
```

### Gateway

```text
192.168.1.200
```

---

# Smart Inter-Campus Research Collaboration Network

![Smart Inter-Campus Research Collaboration Network](images/ospf_story.png)

**Figure 1:** OSPF-based inter-campus communication network connecting two research laboratories.

---

# Network Topology

```text
Campus A Research Lab

PC0 (Aravinth N)
PC1 (Vignesh Kumar)

       |
    Switch0
       |
    Router2
       |
====================
 Serial Link
 (12.1.1.0/24)
====================
       |
    Router5
       |
    Switch1
       |
PC2 (Maadeash K)
PC3 (Karthik Raj)

Campus B Research Lab
```

---

# IP Addressing Scheme

| Device | Interface | IP Address |
|----------|----------|----------|
| Router2 | FastEthernet0/0 | 192.168.0.200 |
| Router2 | Serial2/0 | 12.1.1.1 |
| Router5 | FastEthernet0/0 | 192.168.1.200 |
| Router5 | Serial2/0 | 12.1.1.2 |

---

# Router2 Configuration

```bash
enable
configure terminal

interface fa0/0
ip address 192.168.0.200 255.255.255.0
no shutdown

interface serial2/0
ip address 12.1.1.1 255.255.255.0
no shutdown

router ospf 1

network 192.168.0.0 0.0.0.255 area 0
network 12.1.1.0 0.0.0.255 area 0
```

---

# Router5 Configuration

```bash
enable
configure terminal

interface fa0/0
ip address 192.168.1.200 255.255.255.0
no shutdown

interface serial2/0
ip address 12.1.1.2 255.255.255.0
no shutdown

router ospf 1

network 192.168.1.0 0.0.0.255 area 0
network 12.1.1.0 0.0.0.255 area 0
```

---

# OSPF Neighbor Formation

After configuration, Router2 and Router5 begin exchanging OSPF Hello packets.

The routers progress through multiple states:

1. Down
2. Init
3. 2-Way
4. ExStart
5. Exchange
6. Loading
7. Full

When the routers reach the FULL state, they become OSPF neighbors and exchange routing information successfully.

---

# OSPF Neighbor Formation Process

![OSPF Neighbor Formation](images/ospf_neighbor_formation.png)

**Figure 2:** OSPF adjacency establishment between Router2 and Router5.

---

# Simulation Output

```text
OSPF-5-ADJCHG:
Nbr 192.168.1.200 on Serial2/0
from LOADING to FULL
```

### Observation

The above output confirms that Router2 and Router5 successfully formed an OSPF adjacency relationship and exchanged routing information.

---

# Research Data Communication Scenario

Assume Aravinth N (PC0) has completed a simulation report related to the Smart Autonomous Traffic Monitoring System.

The report must be shared with Maadeash K (PC2) located in Campus B.

The communication process occurs as follows:

### Step 1

Aravinth generates the research report on PC0.

### Step 2

Switch0 forwards the packet to Router2.

### Step 3

Router2 checks the OSPF routing table.

### Step 4

OSPF identifies Router5 as the next-hop router.

### Step 5

The packet is transmitted through the serial link.

### Step 6

Router5 receives the packet.

### Step 7

Router5 forwards the packet to Switch1.

### Step 8

Switch1 delivers the packet to PC2.

### Step 9

Maadeash receives the report successfully.

---

# OSPF Packet Flow Diagram

![Research Data Packet Flow Through OSPF Network](images/ospf_packet_flow.png)

**Figure 3:** End-to-end packet forwarding using OSPF dynamic routing.

---

# Working Principle of OSPF

OSPF operates using the Link State Routing Algorithm.

### Main Functions

- Neighbor discovery
- Link state advertisement
- Topology database creation
- Shortest path calculation
- Dynamic route updates

### OSPF Workflow

```text
Discover Neighbor
        ↓
Exchange Link-State Information
        ↓
Build Topology Database
        ↓
Calculate Shortest Path
        ↓
Update Routing Table
        ↓
Forward Packets
```

---

# Advantages of OSPF

- Dynamic route discovery
- Fast convergence
- Automatic route updates
- Loop-free routing
- Efficient path selection
- Scalable architecture
- Reliable communication
- Supports large networks

---

# Applications of OSPF

- University campus networks
- Research institutions
- Enterprise networks
- Data centers
- Government organizations
- Internet Service Providers (ISPs)
- Smart city communication systems

---

# Result

The OSPF routing protocol was successfully configured between Router2 and Router5 using Cisco Packet Tracer.

The routers established OSPF adjacency, exchanged routing information automatically, and enabled successful communication between Campus A and Campus B.

The simulation verified the capability of OSPF to provide dynamic routing and efficient packet delivery.

---

# Conclusion

This project successfully demonstrated the implementation of Open Shortest Path First (OSPF) routing in a real-time inter-campus research collaboration network.

The protocol enabled automatic route discovery, shortest path selection, route maintenance, and reliable communication between geographically separated research laboratories.

The simulation confirms that OSPF is an efficient and scalable routing protocol for modern network infrastructures.

---

# References

1. Cisco Networking Academy – Routing and Switching Essentials
2. Behrouz A. Forouzan – Data Communications and Networking
3. Andrew S. Tanenbaum – Computer Networks
4. RFC 2328 – OSPF Version 2
5. Cisco Packet Tracer Documentation

---



# Thank You

### Dynamic Routing Through OSPF for Smart Inter-Campus Research Communication
