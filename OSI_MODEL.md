OSI = Open Systems Interconnection

There are seven layers

**7. Application Layer**

- protocolos: HTTP/SMTP/IMAP/POP3/FTP/SSH

**6. Presenation Layer**

- Encoding/Encryption/Serialization/JSON

**5. Session Layer**

- RPC/NETBIOS/Session Management

**4. Transport Layerr**

- TCP/UDP/QUIC
- Ports
- Data Units (TCP - Segment, UDP - Datagram)

**3. Network Layer**

- IP/ICMP

**2. Data Link Layer**

- MAC/Ethernet

**1. Physical Layer**

- Electrical Signals / Radio Waves
- Binary

### Example

**Request**

- HTTP GET /profile
- Autorization: Bearer xyz
- X-Header: xyz

**Process**

> Source

TCP Segment

- source port: 3000
- chuck
- destination port: 443

IP Packet

- source ip: 192.168.1.1
- destination ip: 10.0.0.1

Data Link Frame

- source mac: MAC_SRP
- destination mac: MAC_DG

Signal to transmit

- Binary

> Router

- Transmit the signals

> Destination

Data Link Frame

- source mac: MAC_SRP
- destination mac: MAC_DG

IP Packet

- source ip: 192.168.1.1
- destination ip: 10.0.0.1

TCP Segment

- source port: 3000
- chuck
- destination port: 443
