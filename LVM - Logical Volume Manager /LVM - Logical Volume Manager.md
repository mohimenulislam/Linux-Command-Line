
#### Create the volume group with name `myvolume` with `8MiB P.E.` and create the lvm name `mydatabase` with the `100P.E.` format this lvm with ext4 and create a directory `/database` & mount this lvm permanently on `/database`. 

##### Create the Physical Volume (PV): 

- Add Hard Disk from VMware/Virtual Box as per requirement.

 Check disk partitions
```bash
lsblk
fdisk -l    # manipulate disk partition table, -l:list 
```

Enter the disk that was created earlier from VMware/VirtualBox or another disk where I need to create the LVM.
```bash
fdisk /dev/sdb

```

Partiton size will be 850-900 mb because 8MiB PE * 100 PE = 800MB.
- Press `m` for help.
- Press `g` for a new empty GPT partition table (In exam no need to change partition table).
- Press `n` for add a new partition.
- Partition number (1-128, default 1): Enter
- First sector (2048-4194270, default 2048): Enter
- Last sector, +/-sectors or +/-size{K,M,G,T,P} (2048-4194270, default 4194270): +850M
- Press `t` to change the partition type to LVM.
- Type 30 for LVM partition.
- Press `p` for print the partition table.
- Press `w` for write table to disk and exit

Create PV - Physical Volume
```bash
pvcreate /dev/sdb1 
pvdisplay 
```

##### Create the Volume Group (VG): 
Create the `myvolume` volume group using the physical volume created earlier in the previous step

```bash
vgcreate myvolume -s 8M /dev/sdb1
vgdisplay
```

Create the Logical Volume (LV):
Create the `mydatabase` logical volume within the "myvolume" volume group with 100 
P.E. (physical extents):
