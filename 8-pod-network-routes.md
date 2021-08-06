# Provisioning Pod Network Routes

Pods scheduled to a node receive an IP address from the node's Pod CIDR range. At this point pods can not communicate with other pods running on different nodes due to missing network routes.

In my case, I need to create static route that maps pod CIDR to the node's internal IP address

## Routes
in my case, my host is windows, run as administrator in powershell:

```
route ADD 10.200.0.0 MASK 255.255.255.0 192.168.186.131
route ADD 10.200.1.0 MASK 255.255.255.0 192.168.186.132
```
