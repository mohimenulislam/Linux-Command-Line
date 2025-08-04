# File Permission 

## Viewing Permissions & Ownership
- `ls -l` → List files with permissions, owner, and group
- `ls -ld directory_name` → Show directory permissions
- `stat filename` → Detailed file permissions and ownership


![image alt](https://github.com/mohimenulislam/Linux-Command-Line/blob/0907537b8a64a24126f4fb0e007c25f5da923a6c/Img/file%20permission.png)

Identifier |	File Type 
--- | --- |
 `d` | Directory
 `-` | REGULAR File
 `c` | Character Device
 `l` | Link
 `s` | SOCKET File
 `p` | Pipe
 `b` | Block Device

### There are 3 type of permissions 

- `r` - `4` - Read
- `w` - `2` - Write
- `x` - `1` - Execute
- `-` - No Permission 

### User, group, and others Option in Linux File Permission

![image alt](https://github.com/mohimenulislam/Linux-Command-Line/blob/54248661b4dce832f420629675f5624a18223e6d/Img/file%20permission1.png)

![image alt](https://github.com/mohimenulislam/Linux-Command-Line/blob/54248661b4dce832f420629675f5624a18223e6d/Img/file%20permission2.png)


Reference |	Class  | 	Description
--- | ---| --- |
`u` | user | The user permissions apply only to the owner of the file or directory.
`g` |  group | The group permissions apply only to the group that has been assigned to the file or directory.
`o` | other | The group permissions apply only to the group that has been assigned to the file or directory.
`a` | all | All three (owner, groups, others)


 - The first character `-` which means it’s a file, `d` which means it’s a directory.
 - Permission settings: `rw-r--r--`


### Default Permission of `File` / `Directory` created from `root`

```bash
d rwx r-x r-x. 3 root root   18 Oct  1 13:41 test
   7   5   5
   
- rw- r-- r--. 1 root root    0 Oct  1 19:16 test.txt
   6   4   4
```



### Default Permission of `File` / `Directory` created from `user`

```bash
d rwx rwx r-x. 2 alex alex 6 Oct  1 19:25 test
  7   7   5
- rw- rw- r--. 1 alex alex 0 Oct  1 19:25 test.txt
  6   6   4 
```

## Changing File Permissions (chmod)

### Symbolic Mode:

- `chmod u+x file_name` → Add execute permission for user.
- `chmod g-w file_name` → Remove write permission for group.
- `chmod o+r file_name` → Add read permission for others.
- `chmod +x vpc.sh` → Add execute permission for all.
- `chmod go+wx file_name` → Add write & execute permission of group and others.
- `chmod o-rwx /common/admin` → Remove permission from others.
- `chmod g+s /common/admin` → Files created in "/common/admin/" automatically have group ownership.
  
![image](https://github.com/mohimenulislam/Linux-Command-Line/blob/9c9d61dd3fb03ecd7104b0a72a40bf03bff37ebd/Img/groupownershipchange.png)

### Numeric Mode (Octal Representation):

- `chmod 644 file_name` → rw-r--r-- (Owner: Read & Write, Group: Read, Others: Read)
- `chmod 755 file_name` → rwxr-xr-x (Owner: Full, Group & Others: Read & Execute)
- `chmod 700 file_name` → rwx------ (Only owner has full access)
- `chmod -R 777 directory_name` → Apply recursively to a directory

## Changing Ownership (chown)
- `chown user file_name` → Change file owner
- `chown user:group file_name` → Change owner and group
- `chown :group_name file_name` → Change only group
- `chown :group_name /common/admin` Change group ownership of /common/admin
- `chown -R user:group directory/` → Change recursively


## Changing Group Ownership (chgrp)
- `chgrp group_name file_name` → Change group of a file
- `chgrp -R group_name directory/` → Change group recursively



