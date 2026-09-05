Root Host -> An way to send data out side of LAN

Example: Mobile -> Router - - -> Laptop

---

[Router A]

- Host Network A: 192.168.1.50
- Host Network B: 192.168.2.50
  [Network A]
- Host A: 192.168.1.2
- Host B: 192.168.1.3
- Host C: 192.168.1.4
  [Network B]
- Host A: 192.168.2.2
- Host B: 192.168.2.3
- Host C: 192.168.2.4

Case: Network A -> Host A wants to send data to Network A -> Host C

1. 192.168.1.2 & 255.255.255.0 = 192.168.1.0
2. 192.168.1.4 & 255.255.255.0 = 192.168.1.0
3. {1.} == {2.} means in same network

Case: Network A -> Host A wants to send data to Network B -> Host C

1. 192.168.1.2 & 255.255.255.0 = 192.168.1.0
2. 192.168.2.4 & 255.255.255.0 = 192.168.2.0
3. {1.} == {2.} means not in same network
4. send to DEFAULT_GATEWAY
5. send to Network B -> Host C
