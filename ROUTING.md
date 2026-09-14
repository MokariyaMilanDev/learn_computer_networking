Routing in action

## Structure of Network

- Internet
- - Router (Local) (Public IP: 2.3.4.5)
- - - Network 1 (IP: 192.168.0.1) (Switch)
- - - - A (IP: 192.168.0.3)
- - - - B (IP: 192.168.0.2)
- - - - C (IP: 192.168.0.4)
- - - - D (IP: 192.168.0.5)
- - - Network 2 (IP: 192.168.1.1)
- - - - X (IP: 192.168.1.5)
- - Router P (Public IP: 1.2.3.4)
- - Router Q (Public IP: 5.6.7.8)
- - Router AWS (3.4.5.0)
- - - Network AWS
- - - - EC2 (3.4.5.6)

**Case 1**

A want to send data to D

- Ethernet Frame: A's MAC <-> 10.0.0.3 <-> DATA <-> 10.0.0.5 <-> D's MAC
- 1. Subnet Mask
- - check does ip exists in the same network
- 2. ARP for MAC - switch will help
- - A will broadcast to every hosts by using switch
- - - Switch will smartly done work
- - Both host parties save each IP and MAC in ARP table

**Case 2**
C want to send data to X

- Ethernet Frame: C's MAC <-> 10.0.0.4 <-> DATA <-> 192.168.1.5 <-> X's MAC
- - C apply subnet mask and get to know host X is not in the our network
- - - Now, an ARP request that 'What is MAC of Default Getway?'
- - - - Each store IP and MAC pair in the ARP table
- - - C's MAC <-> 10.0.0.4 <-> DATA <-> 192.168.1.5 <-> Default Getway's MAC
- - Router/Default Gatway
- - - Apply subnet mask and get to know host X is part of network
- - - Now, an ARP request that 'What is MAC of X'
- - - - Each store IP and MAC pair in the ARP table
- - - C's MAC <-> 10.0.0.4 <-> DATA <-> 192.168.1.5 <-> X's MAC

**Case 3**
C want to send data to AWS

- Ethernet Frame: C's MAC <-> 10.0.0.4 <-> DATA <-> 3.4.5.6 <-> DG's MAC
- C will appy subnet mask
- - will send to switch
- switch will ARP request
- - will send to Router
- router will apply subnet mark
- - source from local to router
- - UPDATE: DG's MAC <-> 2.3.4.5 <-> DATA <-> 3.4.5.6 <-> RP's MAC
- Router P will process
- - UPDATE: RP's MAC <-> 2.3.4.5 <-> DATA <-> 3.4.5.6 <-> RQ's MAC
- Router Q will process
- - UPDATE: QP's MAC <-> 2.3.4.5 <-> DATA <-> 3.4.5.6 <-> RAWS's MAC
- Router ASW will process
- - UPDATE: RAWS's MAC <-> 2.3.4.5 <-> DATA <-> 3.4.5.6 <-> EC2's MAC
- EC2 will process

- ! Frame travel over network never change destination IP
