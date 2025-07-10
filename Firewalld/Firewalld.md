## Firewall

```
firewall-cmd --list-all
firewall-cmd --permanent --add-service=http
firewall-cmd --permanent --remove-service=http


firewall-cmd --permanent --add-port=80/tcp

firewall-cmd --reload
firewall-cmd --state

firewall-cmd --list-all-zones  # level of trust


```
If an interface or source is not explicitly assigned to any zone, incoming traffic will be handled by the default zone, which is typically the public zone.
