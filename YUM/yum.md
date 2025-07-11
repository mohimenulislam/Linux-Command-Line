# YUM - Yellowdog Updater, Modified

## 🧩 Package Installation & Removal
- `yum install package-name` — Install a package.
- `yum remove package-name` — Uninstall/remove a package.
- `yum update` — Update all packages to the latest version.
- `yum update package-name` — Update a specific package.
- `yum check-update` — Show packages with available updates.

## 🔍 Searching & Info
- `yum search keyword` — Search for a package using a keyword.
- `yum info package-name` — Display detailed info about a package.
- `yum list` — List all available packages.
- `yum list installed` — List installed packages.
- `yum list available` — List only available packages.
- `yum list updates` — List all packages that can be updated.


## 📦 Group Package Management
- `yum group list` — List available and installed package groups.
- `yum groupinstall "Group Name"` — Install a group of related packages.
- `yum groupremove "Group Name"` — Remove a group of related packages.
- `yum groupinfo "Group Name"` — Show details about a group.

## 🛠️ Repository Management
- `yum repolist` — List all enabled repositories.
- `yum repolist all` — List all repositories (enabled + disabled).



## 🧪 Troubleshooting & Verification
- `yum check` — Check for problems in RPM DB.
- `yum history` — Show yum transaction history.
- `yum history list` — List all transactions.
- `yum history info [ID]` — Show info about a specific transaction.
- `yum history undo [ID]` — Undo a transaction by ID.
- `yum clean all` — Clear all cached files from yum.
- `yum clean metadata` — Clear just the repository metadata.
- `yum clean packages` — Remove cached packages.
- `yum deplist package-name` — Show dependencies for a package.

## 🧰 Advanced Options
- `yum provides /path/to/file` — Find which package provides a file.
- `yum shell` — Start an interactive yum shell.
- `yum localinstall package.rpm` — Install a local RPM with dependencies.
- `yum makecache` — Generate the metadata cache.
- `yum whatprovides command/file` — Find package that provides a command.
