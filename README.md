# Linux Command Line

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


- `cp testfile.txt /tmp`: Copy testfile.txt file from currentdirectory to /tmp <br>
- `rm testfile.txt`:	Delete testfile.txt <br>
- `rm testfile.txt testfile1.txt`: Delete multiple files, required permission <br>
- `rm -rf testfile.txt testfile1.txt`: Delete multiple files, no permission required
- `rm -rf *`:	Delete all files, directories<br>
- `mv testfile /tmp`: Move testfile.txt from current directory to /tmp	<br>
- `mv testfile newtestfile`: Rename files,directories	<br>
- `mv testfile.txt ../`: Move file to previous directory	<br>	
- `mv * ../`: Move all files to previous directory <br>
- `mv testfolder1/* testfolder2`: Root has two directories name testfolder1, testfolder2, move all file from testfolder1 directory to testfolder2 directory <br>



- `mv testfolder1/!(folder1) testfolder2`: Suppose root has two directories testfolder1 and testfolder2. testfolder1 has five directories folder 1, folder2, folder3, folder4, folder5. You have to move all folder except folder1 from testfolder1 to testfolder2. mv SOURCE_DIRECTORY/!(unwanted_filename) TARGET_DIRECTORY	 <br>


