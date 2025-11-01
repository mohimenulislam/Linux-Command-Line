
## NFS

NFS Server >> 192.168.0.10
NFS Client >> 192.168.0.11

### NFS Server
#### Install NFS Packages
```bash
yum install nfs-utils -y

sudo systemctl enable nfs-server
sudo systemctl start nfs-server
sudo systemctl status nfs-server

```

#### Create a Shared Directory
```bash
sudo mkdir -p /shared/data
sudo chmod 777 /shared/data
```
#### Define the Export in /etc/exports
```bash
vi /etc/exports
```
Add this line:
```bash
/shared/data 192.168.0.11/24(rw)
```

#### Apply the Export Rules
```bash
exportfs -rav
```

#### Firewall and Security
```bash
sudo firewall-cmd --permanent --add-service=nfs
sudo firewall-cmd --permanent --add-service=mountd
sudo firewall-cmd --permanent --add-service=rpc-bind
sudo firewall-cmd --reload
```

### Configure Client

#### Install NFS Packages
```bash
yum install nfs-utils -y

sudo systemctl enable nfs-server
sudo systemctl start nfs-server
sudo systemctl status nfs-server
```
#### Create a mount point:
```bash
mkdir -p /mnt/nfs/data
```
#### Mount the shared directory:
```bash
mount 192.168.0.10:/shared/data /mnt/nfs/data
```
#### Check:
```bash
df -h | grep nfs
```

### Test
#### On Server (192.168.0.10)
```bash
echo "Hello from server" > /shared/data/test.txt
```

#### On Client (192.168.0.11):
```bash
cat /mnt/nfs/data/test.txt
```
