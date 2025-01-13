
#### Create the volume group with name `myvolume` with `8MiB P.E.` and create the lvm name `mydatabase` with the `100P.E.` format this lvm with ext4 and create a directory `/database` & mount this lvm permanently on `/database`. 

##### Create the Physical Volume (PV): 
- Add Hard Disk from VMware/Virtual Box as per requirement.
- 1st create partitions by fdisk and disk type 30(lvm). 
- and partiton size 850-900 mb because 8MiB PE * 100 PE = 800MB.


```bash
lablk
fdisk -l 
fdisk /dev/sdb 
```
