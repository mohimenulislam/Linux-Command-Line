# Linux Command Line

## File Maintenance Commands

- `cp`: ccopy files and directories <br>
- `mv`: move (rename) files <br>
- `mkdir`: remove empty directories <br>
- `rmdir`: remove empty directories <br>
- `rm`: remove files or directories <br>
- `rm-r`: remove directories and their contents recursively <br>
- `rm -rf`: remove directories and their contents recursively and force, ignore nonexistent files and arguments, never prompt <br>
- `chgrp`: chgrp - change group ownership <br>
- `chown`: change file owner and group <br>

Copy testfile.txt file from currentdirectory to /tmp
```bash
cp testfile.txt /tmp
```
Delete testfile.txt
```bash
rm testfile.txt	
```
Delete multiple files, required permission
```bash
rm testfile.txt testfile1.txt
```
Delete multiple files, no permission required
```bash
rm -rf testfile.txt testfile1.txt
```
Delete all files, directories

```bash
rm -rf *	
```
Move testfile.txt from current directory to /tmp
```bash
mv testfile /tmp	
```
Rename files,directories
```bash
mv testfile newtestfile	
```
Move file to previous directory
```bash
mv testfile.txt ../		
```
Move all files to previous directory
```bash
mv * ../
```
Root has two directories name testfolder1, testfolder2, move all file from testfolder1 directory to testfolder2 directory
```bash
mv testfolder1/* testfolder2
```
