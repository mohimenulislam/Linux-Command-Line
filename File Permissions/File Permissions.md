
- `chmod`:- change file mode bits


How to Check the Permission of Files in Linux
```bash
ls -l <file_name>
```

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
