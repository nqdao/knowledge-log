You can "disable" (or stop) the iptables firewall by setting the default policies on all standard chains to "ACCEPT", and flushing the rules.

```
iptables -P INPUT ACCEPT
iptables -P OUTPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -F
```
