## Hard links and soft links in Linux

There are two types of links :

- Soft Link or Symbolic links
- Hard Links

Hard links and soft links are both types of links in Linux that point to files.

Hard Links | Soft Links
--- | --- |
The `ln` command is used to make a hard link in Linux. | The `ln -s` command is used to make a soft link in Linux.
It is a copy of the original file that serves as a pointer to the same file, allowing it to be accessed even if the original file is deleted or relocated. | It is a short pointer file that links a filename to a pathname. It's nothing more than a shortcut to the original file, much like the Windows OS's shortcut option
It has a similar inode number to the target file. | It has a different inode number.
It is not allowed the relative path. | It allows both relative and absolute paths.
It is faster. | It is slower.
It may only link to a file. | It may link both to a directory or a file.
It remains valid even if the target file is deleted. | It becomes invalid when the originating file is deleted.

> [!Note]
> - An Inode is a data structure containing metadata about the files. Following contents are stored in the Inode from a file: `User ID of file` , `Group ID of file` , `Device ID` , `File size` , `Date of creation` ,  `Permission` , `Owner of the file` , `File protection flag` , `Link counter to determine number of hard links`
> - `iNode` - In Linux, an inode number is a unique identifier for a file or directory within a filesystem. It's like a file's internal ID number, used by the operating system to locate and manage the file
> - When we create a file, it create a location in disk to store the file. And this location indicate the iNode number. Whey we try to modify a file ,it first goes to iNode table then fetch the data.
> - Think of the hard disk as being divided into blocks. Some of these blocks are allocated to store the inode table. Each entry in the table represents an inode, which contains metadata about a file.


Each iNode has a unique number and Inode number can be seen with the help of ls -li command.
```bash
ls -li
```

Display file or file system status
```bash
stat file.txt  # The stat command in Linux is a powerful tool used to display detailed information about a file or file system. It's like a file inspector, giving you a comprehensive report on various attributes.
```


