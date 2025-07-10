## Firewall

```
firewall-cmd --list-all
firewall-cmd --permanent --add-service=http
firewall-cmd --permanent --remove-service=http


firewall-cmd --permanent --add-port=80/tcp

firewall-cmd --reload
firewall-cmd --state

firewall-cmd --list-all-zones  # level of trusted


```
