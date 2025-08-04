

### 👥 Account Types in Linux

| Account Type         | UID Range    | Description                                                                 |
|----------------------|--------------|-----------------------------------------------------------------------------|
| **Root Account**     | `0`          | Superuser with full administrative control. Can execute any command.       |
| **System Account**   | `1–999` or `1–999` | Used by the OS or installed services (e.g., `sshd`, `mysql`). No login shell. |
| **Regular User**     | `1000+`      | Created for human users. Can log in, store files, and run processes.       |
| **Service Account**  | `1–999`      | Subset of system accounts, used to run background services.                |






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
