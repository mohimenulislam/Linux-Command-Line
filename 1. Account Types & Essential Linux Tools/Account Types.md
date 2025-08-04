
### Account Types
- `Superuser Account`: Ex: root, UID=0. In Linux, the superuser account is known as your system’s default administrator root. Every Linux system must have at least one root user account. As part of administrative privileges. Unlike other accounts, the home directory of the superuser is in the top-level directory, located at `/root`
- `User Account`: Ex: Bob, Michael, Dave. On modern Linux systems, regular users have UIDs with four-digit numbers starting at 1000. In fact, the first user account you create on your system will usually have UID 1000. By default, regular user accounts have their home directory in the /home directory.
- `System Account`: Ex: ssh, mail, UID 1<99 OR between 500-999. The operating system creates system accounts during its installation. System accounts are used for running operating system components but do not run with superuser privileges.
- `Service Account`: Ex: nginx, mercury, three-digit UID, between 100 and 999. Just like system accounts, service accounts don't have a home folder or a default shell. They are assigned /sbin/nologin to refuse logins.

![AccountTypes](https://github.com/user-attachments/assets/f56415fa-653e-4069-819e-dd818b18e8b8)

User shell prompt<br>
<img width="179" alt="Screenshot_71" src="https://github.com/user-attachments/assets/3bdd57f1-3a5b-4aa1-80cd-d71abf73c3ad"> <br>
Root user shell prompt<br>
<img width="161" alt="Screenshot_11" src="https://github.com/user-attachments/assets/94b8576b-f605-4675-9f06-30880f0049ba">


### Basic Shell Navigation

| Command    | Purpose                      |
| ---------- | ---------------------------- |
| `pwd`      | Print current directory path |
| `ls`       | List files/directories       |
| `cd /path` | Change directory             |
| `cd ..`    | Go up one directory          |
| `cd ~`     | Go to home directory         |


### Text Viewing Command

| Command          | Description                                         |
|------------------|-----------------------------------------------------|
| `cat file`       | Display the entire contents of a file              |
| `less file`      | Scroll up/down through file content (more advanced)|
| `more file`      | View file one page at a time (forward only)        |
| `head file`      | Show the first 10 lines of a file                  |
| `head -20 file`| Show the first 20 lines of a file                  |
| `tail file`      | Show the last 10 lines of a file                   |
| `tail -20 file`| Show the last 20 lines of a file                   |
| `tail -f file`   | Continuously monitor a file (e.g., logs)           |

### Manual Pages

| Command          | Description               |
| ---------------- | ------------------------- |
| `man command`    | Full manual for a command |
| `info command`   | Extended documentation    |
| `command --help` | Quick options summary     |
