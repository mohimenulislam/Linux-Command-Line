
- `chmod`:- change file mode bits


How to Check the Permission of Files in Linux
```bash
ls -l <file_name>
```

### There are 3 type of permissions 

- `r` - `4` - read
- `w` - `2` - write
- `x` - `1` - execute 

### User, group, and others Option in Linux File Permission

Reference |	Class  | 	Description
--- | ---| --- |
`u` | user | The user permissions apply only to the owner of the file or directory.
`g` |  group | The group permissions apply only to the group that has been assigned to the file or directory.
`o` | other | The group permissions apply only to the group that has been assigned to the file or directory.
`a` | all | All three (owner, groups, others)


 - The first character `-` which means it’s a file, `d` which means it’s a directory.
 - Permission settings: `rw-r--r--`
