
## Read and Use System Documentation

A Linux shell contains two types of commands: 
- internal commands
- external commands.

#### help Command in Linux 
In Linux, the help command is a valuable tool for understanding and using built-in internal shell commands. It provides quick and concise information about how to use these commands effectively.
```bash
ls --help

help help 

```

#### journalctl Command in Linux
journalctl is a powerful command-line tool in Linux systems that provides access to the systemd journal, a centralized logging system.
journalctl - Query the systemd journal

```bash
journalctl--help
```

#### man Command in Linux
man - an interface to the system reference manuals
```bash
man man
man mkdir
man journalctl
```

#### Finding all Commands Related to a Keyword
In Linux, the apropos command is a powerful tool that helps users find commands when they don't remember the exact name but have some keywords related to their function.

apropos - search the manual page names and descriptions
```bash
apropos director # Search for directory related command
# or
apropos "director"  # Search for directory related command
```

#### systemctl command in linux
- `systemctl` is the command-line tool you use to interact with `systemd`
- `systemctl` is the command-line utility used to control and manage `systemd`
- `systemctl` commands to tell `systemd` what to do, like starting or stopping services, checking their status, and configuring system settings.
- systemctl - Control the systemd system and service manager
```bash
systemctl [TAB]
```

