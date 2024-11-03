# Linux Command Line

Table of Contents 
====================
* [Manage User & Group](manage-user-&-groups)<br>
* [File Maintenence Commands](#file-maintenance-commands)

## Manage User & Group
### Files
- `/etc/group`: Group account information.
- `/etc/gshadow`: Secure group account information.
- `/etc/login.defs`: Shadow password suite configuration.
- `/etc/passwd`: User account information.
- `/etc/shadow`: Secure user account information.
- `/etc/subgid`: Per user subordinate group IDs.
- `/etc/subuid`: Per user subordinate user IDs.
- `last`: Display the record of all logged users.






Create a User
```
useradd natasha
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



Create a new user account named "alex" and assign it the user ID 1015
```
Useradd alex -u 1015
```

Lock a user named alex
```
passwd -l alex
```

Unlock a User named alex
```
passwd -u faisal
```

Create "nologin" user
```
useradd -s /sbin/nologin nologin_user
```

Create a group named sysadmin
# getent group sysadmin	// check this group is created or not
# cat /etc/group | grep sysadmin 
# groupadd sysadmin		//group add

A user natasha who belongs to sysadmin as a secondary group. 
# id natasha 
# useradd Natasha // 
# usermod -aG sysadmin natasha

Multiple user add to group
# gpasswd -M [user1],[user2] [group_name]
# gpasswd -M [faisal],[afif] [support_team]
		      user name 	group name

User remove from froup 
# gpasswd -d [user] [group]
Nologin user create
# useradd -s /sbin/nologin nologin_user
User shell change 
# usermod -s /bin/bash nologin_user
# usermod harry -s /sbin/nologin 
User Lock
#  usermod -L faisal	
User Unlock
# usermod -U faisal

Change user password expiry information
# chage alex
# chage -l alex	//Show account aging information.
# chage -M 90 alex	//password expire after 90 days





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


