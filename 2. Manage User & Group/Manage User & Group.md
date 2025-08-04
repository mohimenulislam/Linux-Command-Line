
## Manage User & Group


### Necessary Files of User and Group
- `/etc/group`: Group account information.
- `/etc/gshadow`: Secure group account information.
- `/etc/login.defs`: configuration file that defines the default settings for user account creation and password policies in Linux.
- `/etc/passwd`: User account information. <br>
Ex: `username`:`password`:`UID`:`GID`:`comment`:`home`:`shell` <br>
     `faisal`:`x`:`1000`:`1000`:`faisal`:`/home/faisal`:`/bin/bash` <br>
     <img width="1005" height="191" alt="image" src="https://github.com/user-attachments/assets/65cfbffd-47dd-4914-9942-b7f72c4dd899" />

- `/etc/shadow`: Secure user account information.<br>
Ex: `username`:`password`:`last password change`:`min`:`max`:`warning`:`inactive`:`expired`




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


#### Create a user named `alex`
```
useradd alex
```
#### Check UID & GID
```bash
id alex
``` 	

#### Set password for `alex`
```
passwd alex
```

#### Root password change
```bash
passwd # from root account
# or 
echo 1234 | passwd --stdin root
```

#### Delete a user named `alex`
```bash
userdel alex    # or
userdel -f alex # -f, --force 
```

#### Create a new user account named `alex` and assign it the user ID 1015
```
Useradd alex -u 1015
```

#### Change the user ID `1010` for `alex` user
```bash
usermod -u 1010 alex  # -u, --uid
```


#### Assign user home directory
```bash
useradd -d /home/alex_home alex
```

#### Rename login username
```bash
usermod -l new_username old_username
```

### Search specific user
```bash
cat /etc/passwd | grep faisal  #or
grep -i faisal /etc/passwd

# alex:     x :1000:1000:test:   /home/faisal: /bin/bash
# usrname:pass:uid :gid :comment:homdir      :shell
```

#### Lock a user named `alex`
```bash
passwd -l alex  # --lock This  option is used to lock the password of specified account and it is available to root only. The locking is performed by rendering the          encrypted password into an invalid string (by prefixing the encrypted string with an !). Note that the account is not fully locked  -  the  user  can still log in by other means of authentication such as the ssh public key authentication. Use chage -E 0 user command instead for full account locking.

usermod -L alex   # Lock a user's password. This puts a '!' in front of the encrypted password, effectively disabling the password. You can't use this option with -p or -U.
```

#### Unlock a User named `alex`
```bash
passwd -u alex  

usermod -U alex 
```

#### Create `nologin` user
```
useradd -s /sbin/nologin nologin_user     # -s, --shell
```

#### User shell change to nologin
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
Create sysadmin group and set gid=600
```bash
groupadd -g 600 sysadmin     # or
groupadd sysadmin -g 600
```
Change group ID
```bash
groupmod -g 1050 sysadmin
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
