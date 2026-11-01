# Two Office OSPF Routing — Project 7
A Cisco Packet Tracer lab connecting Dublin and Cork using single-area OSPF. This extends my static-routing lab by replacing manual routes with OSPF route learning.

![Dublin and Cork topology](screenshots/Topology.png)

## Network design
| Segment | Subnet | Router address(es) |
|---|---|---|
| Dublin LAN | 192.168.10.0/24 | 192.168.10.1 |
| Router link | 10.0.0.0/30 | 10.0.0.1 and 10.0.0.2 |
| Cork LAN | 192.168.20.0/24 | 192.168.20.1 |

Two Cisco 2911 routers, two 2960 switches and two PCs. Router G0/0 serves each LAN; G0/1 links the routers. Both participating interfaces on each router use OSPF area 0. PC addresses are 192.168.10.11 and 192.168.20.11, each using its local .1 gateway.

## Work completed
- Removed the previous static routes and enabled OSPF process 1.
- Verified a FULL OSPF neighbour relationship from Cork.
- Confirmed OSPF routes to the remote LANs.
- Tested PC communication in both directions: 4/4 replies, 0% loss each way.
- Fixed Cork's incorrect OSPF network statement, which prevented its LAN being advertised.
- Saved both router configurations.

## Files
- [Packet Tracer project](topology/Project-7-Two-Office-OSPF.pkt)
- [Router configurations and commands](configurations/)
- [Address table](addressing/IP-and-Port-Table.csv)
- [Neighbour, route and ping evidence](verification/)
- [Troubleshooting and learning notes](documentation/Troubleshooting-and-Learning.md)
- [Combined evidence JPG](screenshots/Project-7-Network-Evidence.jpg)

Open the .pkt in Cisco Packet Tracer. Follow the OSPF command files to reproduce the changes from Project 6.

## Evidence scope
Results are from learner-supplied CLI output and screenshot; the supplied .pkt was not independently executed or internally inspected during packaging. It arrived named Project-6-Two-Office-Static-Routing(1).pkt and is included as Project-7-Two-Office-OSPF.pkt with bytes unchanged. The screenshot is original. JPG command panels are recreated text. Configuration transcriptions omit repeated empty separator lines, preserving all supplied configuration statements. Cork's routing-table snapshot predates its advertisement correction; Dublin's snapshot and the successful pings follow the correction. No backup path or failover demonstration is claimed.
