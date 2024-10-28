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

# 		// 
# mv [current_name] [new_file_name] //rename files,directories
# mv testfile testfile1		//rename testfile to testfile1
# mv testfile ../			//move file to previous directory
# mv * ../				//move all files to previous directory
# mv testfolder1/* testfolder2	//root has two directories name testfolder1, testfolder2, move all file from test1 directory to test2 directory
