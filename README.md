# Linux Command Line

Table of Contents 
====================
* [Manage User & Group](manage-user-&-groups)<br>
  * [Necessary Files of User and Group](necessary-files-of-user-and-group)
  * [User](user)
  * [Group](group)
* [File Maintenence Commands](#file-maintenance-commands)

## Manage User & Group
### Necessary Files of User and Group
- `/etc/group`: Group account information.
- `/etc/gshadow`: Secure group account information.
- `/etc/login.defs`: Shadow password suite configuration.
- `/etc/passwd`: User account information.
- `/etc/shadow`: Secure user account information.
- `/etc/subgid`: Per user subordinate group IDs.
- `/etc/subuid`: Per user subordinate user IDs.
- `last`: Display the record of all logged users.


### User
Create a user named `alex`
```
useradd alex
```
Check UID & GID
```
id [user_name]		
``` 	

Set password 
```
passwd natasha
```

Delete a User
```
userdel natasha
```

Search specific user
```
cat /etc/passwd | grep faisal  #or
grep -i faisal /etc/passwd
```

faisal:    x  	    :1000:1000:test:   /home/faisal: /bin/bash<br>
usrname:pass :uid   :gid   :comment:homdir   :shell

Create a new user account named `alex` and assign it the user ID 1015
```
Useradd alex -u 1015
```

Lock a user named `alex`
```
passwd -l alex
usermod -L alex
```

Unlock a User named `alex`
```
passwd -u alex
usermod -U alex
```

Create `nologin` user
```
useradd -s /sbin/nologin nologin_user
```

User shell change to nologin
```bash
usermod alex -s /sbin/nologin 
```

### Group 

Create a group named `sysadmin`
```bash
getent group sysadmin		# check this group is created or not
cat /etc/group | grep sysadmin 	# check
groupadd sysadmin		# group add
```

A user `alex` who belongs to sysadmin as a secondary group. 
```bash
id alex 	# check id created or not
useradd alex	# id create
usermod -aG sysadmin alex	
```

Multiple user add to group
```bash
gpasswd -M [user1],[user2] [group_name]
```		      

User remove from froup 
```bash
gpasswd -d [user] [group]  # -d delete
```





Change user password expiry information
```bash
chage alex
chage -l alex #Show account aging information.
chage -M 90 alex #password expire after 90 days
```




## File Maintenance Commands
- `cp`: copy files and directories <br>
- `mv`: move (rename) files <br>
- `mkdir`: remove empty directories <br>
- `rmdir`: remove empty directories <br>
- `rm`: remove files or directories <br>
- `rm-r`: remove directories and their contents recursively <br>
- `rm -rf`: remove directories and their contents recursively and force, ignore nonexistent files and arguments, never prompt <br>
- `chgrp`: chgrp - change group ownership <br>
- `chown`: change file owner and group <br>

Copy testfile.txt file from current directory to /tmp <br>
```
cp testfile.txt /tmp
```
Delete testfile.txt <br>
```
rm testfile.txt
```
Delete multiple files, required permission <br>
```
rm testfile.txt testfile1.txt
```
Delete multiple files, no permission required
```
rm -rf testfile.txt testfile1.txt
``` 
Delete all files, directories<br>
```
rm -rf *
```
Move testfile.txt from current directory to /tmp	<br>
```
mv testfile /tmp
```
Rename files,directories	<br>
```
mv testfile newtestfile
```
Move file to previous directory	<br>	
```
mv testfile.txt ../
```
Move all files to previous directory <br>
```
mv * ../
```
Root has two directories name testfolder1, testfolder2, move all file from testfolder1 directory to testfolder2 directory <br>
```
mv testfolder1/* testfolder2
```
Suppose root has two directories testfolder1 and testfolder2. testfolder1 has five directories folder 1, folder2, folder3, folder4, folder5. You have to move all folder except folder1 from testfolder1 to testfolder2. mv SOURCE_DIRECTORY/!(unwanted_filename) TARGET_DIRECTORY	 <br>
```
mv testfolder1/!(folder1) testfolder2
``` 


