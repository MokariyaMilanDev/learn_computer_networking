```bash
traceroute <host>
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

Every time record the response
From MY HOST to ROUTER set TTL=1
From MY HOST to ROUTER A set TTL=2
From MY HOST to ROUTER B set TTL=3
From MY HOST to ROUTER C set TTL=4
From MY HOST to ROUTER D set TTL=5
From MY HOST to AN HOST set TTL=6

**Mean of \*\*\***

- Sometime some host don't reply ICMP request and just drop it tha you can't be able to get to know IP.
