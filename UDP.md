UDP - User Diagram Protocol

- It is layer 3 protocol
- Data Unit is called as Datagram
- We have concept of PORTs to address processes in the host
- It's stateless protocol
- Doesn't require connection establishment (Unlike TCP's 3 Way Handshake)
- Very simple protocol for communication
- Header size of the UDP datagram is only 8 bytes

**Use Cases**

- WebRTC
- Gameplay Traffic
- Video Streaming
- VPN
- DNS
- QUIC

**Example**
HOST A : 127.0.0.1

- service: a on port 5500
- service: b on port 8080
- service: c on port 5432

HOST B: 127.0.0.2

- service: x on port 654
- service: y on port 8080
- service: z on port 9723

Datagram: {{source_ip}} <-> {{source_port}} <-> request <->{{destination_port}} <-> {{destination_ip}}

**Case 1: from service a to service y**
Datagram: 127.0.0.1 <-> 5500 <-> request <-> 8080 <-> 127.0.0.2
