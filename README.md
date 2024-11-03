# Linux Command Line

Table of Contents 
====================
* [Manage User & Group](manage-user-&-groups)<br>
  * [Account Types](account-types) 
  * [Necessary Files of User and Group](necessary-files-of-user-and-group)
  * [Create, modify, and delete user accounts](create-modify-and-delete-user-accounts)
  * [Create, modify, and delete groups](create-modify-and-delete-groups)
  * [Switch Users and sudo Access](switch-users-and-sudo-access)
* [File Maintenence Commands](#file-maintenance-commands)

## Manage User & Group
### Account Types
- `User Account`: Ex: Bob, Michael, Dave
- `Superuser Account`: Ex: root, UID=0
- `System Account`: Ex: ssh, mail, UID<100 OR between 500-100 
- `Service Account`: Ex: nginx, mercury

![AccountTypes](https://github.com/user-attachments/assets/f56415fa-653e-4069-819e-dd818b18e8b8)

User shell prompt<br>
<img width="179" alt="Screenshot_71" src="https://github.com/user-attachments/assets/3bdd57f1-3a5b-4aa1-80cd-d71abf73c3ad"> <br>
Root user shell prompt<br>
<img width="161" alt="Screenshot_11" src="https://github.com/user-attachments/assets/94b8576b-f605-4675-9f06-30880f0049ba">

### Necessary Files of User and Group
- `/etc/group`: Group account information.
- `/etc/gshadow`: Secure group account information.
- `/etc/login.defs`: Shadow password suite configuration.
- `/etc/passwd`: User account information. <br>
Ex: `username`:`password`:`UID`:`GID`:`comment`:`home`:`shell` <br>
     `faisal`:`x`:`1000`:`1000`:`faisal`:`/home/faisal`:`/bin/bash` <br>
- `/etc/shadow`: Secure user account information.<br>
Ex: `username`:`password`:`last password change`:`min`:`max`:`warning`:`inactive`:`expired`
- `/etc/subgid`: Per user subordinate group IDs.
- `/etc/subuid`: Per user subordinate user IDs.



### Create, modify, and delete user accounts
- `useradd`: Creates a new user account.
- `adduser`: Creates a new user account.
- `userdel`: Deletes a user account.
- `usermod`: Modifies an existing user account.
- `chage`: change user password expiry information
- `passwd`: Sets or changes a user's password
- `last`: Display the record of all logged users.
- `id`:  Displays user and group information for a user.
- `whoami`: Displays the currently logged-in username.
- `w`: Shows who is logged in and what they are doing.


Create a user named `alex`
```
useradd alex
```
Check UID & GID
```bash
id faisal
#faisal:    x:1000:1000:test:   /home/faisal: /bin/bash
#usrname:pass:uid :gid :comment:homdir      :shell
``` 	

Set password for `alex`
```
passwd alex
```

Delete a user named `alex`
```bash
userdel alex    # or
userdel -f alex # -f, --force 
```

Create a new user account named `alex` and assign it the user ID 1015
```
Useradd alex -u 1015
```

Change the user ID `1010` for `alex` user
```bash
usermod -u 1010 alex  # -u, --uid

```

Rename login username
```bash
usermod -l new_username old_username
```

Search specific user
```
cat /etc/passwd | grep faisal  #or
grep -i faisal /etc/passwd
```






Lock a user named `alex`
```
passwd -l alex
usermod -L alex
```

Unlock a User named `alex`
```bash
passwd -u alex  # --lock This  option is used to lock the password of specified account and it is available to root only. The locking is performed by rendering the          encrypted password into an invalid string (by prefixing the encrypted string with an !). Note that the account is not fully locked  -  the  user  can still log in by other means of authentication such as the ssh public key authentication. Use chage -E 0 user command instead for full account locking.

usermod -U alex  # Lock a user's password. This puts a '!' in front of the encrypted password, effectively disabling the password. You can't use this option with -p or -U.
```

Create `nologin` user
```
useradd -s /sbin/nologin nologin_user
```

User shell change to nologin
```bash
usermod alex -s /sbin/nologin 
```

### Create, modify, and delete groups

- `groupadd`
- `groupdel`
- `groupmod`

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
gpasswd -d [user] [group]  # -d, --delete
```

Delete group named `sysadmin`
```
groupdel sysadmin
```

Change group name `admin` to `sysadmin`
``` bash
groupmod admin -n sysadmin  #or
groupmod -n sysadmin admin 

```

Change user password expiry information
```bash
chage alex
chage -l alex #Show account aging information.
chage -M 90 alex #password expire after 90 days
```

### Switch Users and sudo Access
File

- `/etc/sudoers`: 
- `visudo`: 

Switch to `root` user 
```
su -
``` 
Switch to `alex` user

```
su - alex
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


