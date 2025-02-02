# ACL - ACL - Linux Access Control

In Linux, an ACL (Access Control List) is a mechanism that allows for more granular control over `file` and `directory` permissions by defining specific access rights for individual `users` and `groups`, going beyond the standard `owner`, `group`, and `other` permissions

## Types of ACLs:
- Access ACLs: Applied directly to a file or directory, specifying the exact permissions for individual users and groups on that specific object. 
- Default ACLs: Set as a template for a directory, automatically applying specified permissions to any new files or directories created within that directory.

## Benefits of using ACLs:
- Enhanced security: Enables more precise control over who can access files and directories, improving data protection. 
- Flexible permissions: Allows for complex permission structures where multiple users or groups need different access levels to the same file.

## How to manage ACLs in Linux:

- `getfacl` - The getfacl command allows you to view the current ACLs on a file or directory. Ex: `getfacel /filename` or `getfacel /directoryname`
- `setfacl` - The setfacl command is used to set and modify ACLs on files and directories.


### Set ACL for a `user`, `group` & `other`   

```bash
setfacl -m u:alex:rwx /file_or_directory
setfacl -m u:alex:rw /file_or_directory
setfacl -m u:alex:--- /file_or_directory    //no permission on this file or directory      
setfacl -m g:groupname:rwx /file_or_directory
setfacl -m o:rwx /file_or_directory


# -m - modify
# u - user
# g - group
# o - other
```

ACL applied file or directory have `+` sign after permission. It's looks like:  
<br>
![image](https://github.com/mohimenulislam/Linux-Command-Line/blob/08358d833a9046fef59e0a482f0da9ef7277a86e/Img/aclfile.png)

### Delete an ACL

#### To remove a specific entry
```bash
setfacl -x u:alex /file_or_directory
```
#### To remove all entries

```bash
setfacl -b /file_or_directory   # b - --remove-all
```


### Default ACL  
To allow all files or directories to inherit ACL entries from the directory it is within

```bash
setfacl -d -m u:root:rwx /common
setfacl -d -m groupname:rwx /common
```


