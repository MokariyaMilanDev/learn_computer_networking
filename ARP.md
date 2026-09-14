ARP = Address Resolution Protocol

- Base on IP return MAC

Host broadcast the ARP request to every host for IP.
Message: What is MAC of <IP> IP?

- Only answer host which have that IP.

- Each host have their own ARP table

**CMDs**

```bash
arp -a // Show ARP Table
```
