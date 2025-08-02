
```bash

nmcli connection add type bond ifname bond0 con-name bond0 mode active-backup 


nmcli connection modify bond0 ipv4.addresses 192.168.0.150/24 ipv4.gateway 192.168.0.1 ipv4.dns 8.8.8.8 ipv4.method manual autoconnect yes


nmcli connection add type ethernet con-name ens160-slave ifname ens160 master bond0
nmcli connection add type ethernet con-name ens256-slave ifname ens256 master bond0

nmcli connection up ens160-slave
nmcli connection up ens256-slave
nmcli connection up bond0

systemctl restart NetworkManager

cat /proc/net/bonding/bond0
```
