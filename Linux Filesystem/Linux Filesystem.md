## Linux Filesystem

### Listing Files and Directories

```bash
ls  # list
ls -a # -a: list all
ls -al  # -l: use a long listing format
ls -alh  #: -h: human-readable
ll 
```
Current working directory
```bash
pwd  # print working directory
```




### Filesystem Tree
![image alt](https://github.com/mohimenulislam/Linux-Command-Line/blob/5d2f78a071cda779e92e3e732b0f127662e77e1d/Img/file_system_tree.png)


### Change directory 
```bash
cd   # Go to home directory
cd / # Go to root directory
cd - # Go to previous directory
cd /var/log
cd /home/aaron
cd .. # parent directory
```

### Creating Files
```bash
touch receipt.txt
touch /home/aaron/receipt.txt
```
### Creating Directories
```bash
mkdir test_directories
```

### File Maintenance Commands
- `cp`: copy files and directories <br>
- `mv`: move (rename) files <br>
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
