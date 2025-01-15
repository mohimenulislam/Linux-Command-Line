
#### Create the volume group with name `myvolume` with `8MiB P.E.` and create the lvm name `mydatabase` with the `100P.E.` format this lvm with ext4 and create a directory `/database` & mount this lvm permanently on `/database`. 

![image alt](https://github.com/mohimenulislam/Linux-Command-Line/blob/3fbfec44a479a4017b18eb6425965069da2ed080/Img/lvm.png)

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
vgcreate myvolume -s 8M /dev/sdb1  # -s: physicalextentsize
vgdisplay
```

##### Create the Logical Volume (LV):
Create the `mydatabase` logical volume within the "myvolume" volume group with 100 
P.E. (physical extents):

```bash
lvcreate -l 100 -n mydatabase myvolume   # 100 P.E.
# or
lvcreate -L 800M -n mydatabase myvolume  # 800 MiB
lvdisplay
```

##### Format the Logical Volume:
Format the "mydatabase" logical volume with the ext4 file system: 

```bash
mkfs.ext4 /dev/myvolume/mydatabase
```
##### Create the Mount Point:
Create a directory `/database` for the mount point.

```bash
mkdir /database 
```

##### Mount the Logical Volume:
Mount the `mydatabase` logical volume to the `/database` directory: 

```bash
mount /dev/myvolume/mydatabase /database/
lsblk
```

##### Make the Mount Permanent:
To ensure the logical volume is mounted permanently on boot, you'll need to add an entry to your `/etc/fstab` file. Open the `/etc/fstab` file in a text editor and add the following line: 

```bash
vi /etc/fstab
# /dev/myvolume/mydatabase /database ext4 defaults 0 0 
# or
# blkid, copy UUID
# UUID="864d6ceb-a5ec-4e54-ae59-b67d6eed156e" /database ext4 defaults 0 0
# UUID is best practice

mount -a # Finally, mount the logical volume again to make sure it's properly mounted
```


#### Delete LVM

```bash
umount /dev/myvolume/mydatabase
umount /dev/myvolume/mydatabase

fdisl /dev/sdb
# press `d` for delete LVM  partition
```

#### Extend or Resize the LVM partition `/dev/myvolume/mydatabase` into 830 MiB from the current size and  mount the  LVM `/dev/myvolume/mydatabase` to a mount point `/database`. The extended partition size must be within approximately `830MiB` to `850MiB`.

```bash
lvresize -rv -L 830M /dev/myvolume/mydatabase 
```


#### Background Study

##### Physical Extent (PE): 
Physical Extent is the smallest unit of storage in a volume group in the Logical Volume Manager (LVM) system. It represents `chunks` of storage space that the volume group is divided into. When you create logical volumes, they are allocated in terms of these physical extents

##### Volume Group (VG):
A Volume Group is a `storage pool` that aggregates one or more `Physical Volumes (PVs)` (e.g., disks, partitions, or RAID arrays) into a single logical unit. Once created, you can allocate storage from this pool to create Logical Volumes (LVs).

 - A VG can include multiple physical devices (e.g., /dev/sda, /dev/sdb).
 - It abstracts the underlying hardware, treating all the combined physical volumes as one large storage unit.
 - You can add more physical volumes to an existing VG to increase its storage capacity.
 - A VG is divided into physical extents (PEs), which are the smallest allocatable units in LVM.

Create Physical Volumes (PVs):
```bash
pvcreate /dev/sda /dev/sdb
```
Create a Volume Group (VG): Combine the physical volumes into a single volume group named `myvolume`
```bash
vgcreate myvolume /dev/sda /dev/sdb
```

Check VG Details: Use the vgdisplay command to see information about the VG:
```bash
vgdisplay myvolume
```

##### Logical Volume (LV):

   
##### MiB
