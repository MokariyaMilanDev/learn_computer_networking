```bash
ping <host>
```

> Flow

MY HOST
IP: 10.0.0.1

ROUTER
IP: 10.0.0.4

-- network --

ROUTER A
IP: 20.0.0.1

ROUTER B
IP: 30.0.0.1

ROUTER C
IP: 40.0.0.1

ROUTER D
IP: 50.0.0.1

<!-- etc. -->

-- google --

AN HOST
IP: 60.0.0.1

- ping create an ICMP echo request
- > 10.0.0.1(source IP) <-> ICMP echo request, TTL=100 <-> destination IP 60.0.0.1
- Now, google will generate an ICMP echo reply request
- > 60.0.0.1(source IP) <-> ICMP echo request, TTL=100 <-> destination IP 10.0.0.1

**TTL**

- Each hope reduce count
