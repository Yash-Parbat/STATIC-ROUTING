📡 Static Routing Implementation – CCNA Practical Project
📘 Project Overview

This project demonstrates a Static Routing configuration using Cisco Packet Tracer, designed as a CCNA-level practical lab.
The topology consists of three routers (R1, R2, R3) interconnected using classless IP addressing (/11 CIDR) and multiple LAN segments connected via switches and end devices.

The goal of this project is to achieve end-to-end connectivity between all networks using manual static routes instead of dynamic routing protocols.

🎯 Objectives

Understand static routing concepts

Implement CIDR-based subnetting

Configure inter-router communication

Verify connectivity using ping and simulation

Practice real-world CCNA routing scenarios

🧠 Key Concepts Used

Static Routing

CIDR (/11 subnet mask)

Classless IP Addressing

Inter-router communication

LAN & WAN segmentation

Cisco IOS routing commands

Network verification & troubleshooting

🗺️ Network Topology Description
🔹 Routers
Router	Role
R1	Left-side edge router
R2	Core / Intermediate router
R3	Right-side edge router

Each router connects to:

One WAN link (router-to-router)

One LAN segment via a switch

🌐 IP Addressing Scheme (CIDR Based)

Subnet Mask for all networks: 255.224.0.0 (/11)

Network	Purpose
10.0.0.0/11	LAN – R1
10.32.0.0/11	R1 ↔ R2 WAN
10.64.0.0/11	LAN – R2
10.96.0.0/11	R2 ↔ R3 WAN
10.128.0.0/11	LAN – R3
🖥️ Devices Used

Routers: Cisco Router-PT (R1, R2, R3)

Switches: Cisco 2960

End Devices:

PCs

Laptops

Server

🔌 Interface Configuration Summary
Router Interfaces
Router	Interface	IP Address
R1	Fa0/1	10.32.0.1
R2	Fa0/0	10.32.0.2
R2	Fa1/0	10.96.0.1
R3	Fa0/1	10.96.0.2
R1 LAN	Fa0/0	10.0.0.1
R2 LAN	Fa0/16	10.64.0.1
R3 LAN	Fa0/18	10.128.0.1
🧾 Static Routing Configuration
🔹 Router R1
ip route 10.64.0.0 255.224.0.0 10.32.0.2
ip route 10.96.0.0 255.224.0.0 10.32.0.2
ip route 10.128.0.0 255.224.0.0 10.32.0.2

🔹 Router R2
ip route 10.0.0.0 255.224.0.0 10.32.0.1
ip route 10.128.0.0 255.224.0.0 10.96.0.2

🔹 Router R3
ip route 10.0.0.0 255.224.0.0 10.96.0.1
ip route 10.32.0.0 255.224.0.0 10.96.0.1
ip route 10.64.0.0 255.224.0.0 10.96.0.1

✅ Verification & Testing
🔍 Commands Used
ping
show ip route
show ip interface brief

✔️ Results

Successful ping between all PCs, laptops, and servers

All routes appear as static (S) in routing table

Full end-to-end connectivity achieved

🧪 Simulation Mode

Packet flow verified using Simulation Mode

ICMP packets successfully traverse:

R1 → R2 → R3

R3 → R2 → R1

