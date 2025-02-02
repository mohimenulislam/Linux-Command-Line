# ACL - ACL - Linux Access Control

In Linux, an ACL (Access Control List) is a mechanism that allows for more granular control over `file` and `directory` permissions by defining specific access rights for individual `users` and `groups`, going beyond the standard `owner`, `group`, and `other` permissions

## Types of ACLs:
- Access ACLs: Applied directly to a file or directory, specifying the exact permissions for individual users and groups on that specific object. 
- Default ACLs: Set as a template for a directory, automatically applying specified permissions to any new files or directories created within that directory.

## Benefits of using ACLs:
- Enhanced security: Enables more precise control over who can access files and directories, improving data protection. 
- Flexible permissions: Allows for complex permission structures where multiple users or groups need different access levels to the same file.

## How to manage ACLs in Linux:

- `getfacl` - The getfacl command allows you to view the current ACLs on a file or directory. 
- `setfacl` - The setfacl command is used to set and modify ACLs on files and directories.

