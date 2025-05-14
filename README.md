# All-in-one-linux-commands
This is my personal linux commands list. You can also have this for reference.

# General Commands
1. **w**: w displays information about currently logged in users and what each user is doing.
```sh
$ w
 14:30:59 up 1 day, 17:03,  1 user,  load average: 1.58, 1.82, 2.06
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
sujata   tty2     tty2             Mon21   21:18m  0.06s  0.04s /usr/lib
```
2. **who** Shows information about currently logged in user.

```sh
$ who
sujata   tty2         2025-05-12 21:28 (tty2)
```
Here, from left, sujata - Login Name of the User
tty2 - User terminal
Mon21   21:18m - Date & Time of login
3. **whoami**: Shows the system’s username
```sh
$ whoami
sujata
```
4. **id**: This command is used to find out user and group names and numeric ID's (UID or group ID) of the current user or any other user in the server.
```sh
$ id
uid=1000(sujata) gid=1000(sujata)groups=1000(sujata), 4(adm), 26(cdrom), 29(sudo),30(dip),45(plugdev),122(lpadmin),132(lxd),133(sambashare)
```
5. **groups**: This command is used to display all the groups for which the user belongs to.
```sh
$ groups
sujata adm cdrom sudo dip plugdev lpadmin lxd sambashare
```
6. **users**: Displays usernames of all users currently logged on the system.
```sh
$ users
sujata
```
7. **last**: Displays a list of all last logged in users. The list can be huge according to the number of user logins.
```sh
$ last
sujata   tty2         tty2             Mon May 12 21:28   still logged in
reboot   system boot  6.8.0-60-generic Mon May 12 21:27   still running
sujata   tty2         tty2             Mon May 12 10:09 - down   (08:45)
reboot   system boot  6.8.0-60-generic Mon May 12 10:08 - 18:54  (08:45)
sujata   tty2         tty2             Wed May  7 19:14 - down  (2+22:38)
reboot   system boot  6.8.0-60-generic Wed May  7 19:13 - 17:52 (2+22:39)
sujata   tty2         tty2             Wed May  7 09:53 - crash  (09:19)
```
8. **lastlog**: This command is used to find the details of a recent login of all users or a particular user pass through as a flag.
```sh
$ lastlog
Username         Port     From             Latest
root                                       **Never logged in**
daemon                                     **Never logged in**
bin                                        **Never logged in**
sys                                        **Never logged in**
sync                                       **Never logged in**
games                                      **Never logged in**
man                                        **Never logged in**
lp                                         **Never logged in**
mail                                       **Never logged in**
news                                       **Never logged in**
```
9. **Man**: This command shows the documentation of every command of linux.
```sh
man ls
```
10. **Date**: Shows date
```sh
$ date
Wednesday 14 May 2025 11:48:01 AM IST
```
11. **History**: History command shows all the previously used terminal commands in a list.
```sh
$ history
 1  ls
 2  man ls
 3  groups
 4  netstat
 5  ping google.com
 6  whoami
```
12. **whatis**: Whatis shows a short particular information about a command.
```sh
$ whatis grep
grep (1)             - print lines that match patterns
```
13. **whereis**: Shows the location of binary, source and manual files for commands.
```sh
$ whereis pwd
pwd: /usr/bin/pwd /usr/share/man/man1/pwd.1.gz
```
14. **alias**: Rename a long repitive command with a short name. For example you can make the command ls -la to any of your suitable name like below example. Then you can use that name to use the command.
```sh
$ ls -la
-rw-rw-r-- 1 sujata sujata    27779 Apr 25 12:33 'image (1).png'
-rw-rw-r-- 1 sujata sujata   139500 Apr 25 15:53 'image (2).png'
-rw-rw-r-- 1 sujata sujata   212441 Apr 10 12:28  image.png
-rw-rw-r-- 1 sujata sujata 14955792 Apr 30 12:01  creation.pdf
-rw-rw-r-- 1 sujata sujata   399313 Apr 16 10:22  kubernetes.pdf
```
Lets have an example for the command **ls -la**
```sh
$ alias ll="ls -la"
$ ll
-rw-rw-r-- 1 sujata sujata    27779 Apr 25 12:33 'image (1).png'
-rw-rw-r-- 1 sujata sujata   139500 Apr 25 15:53 'image (2).png'
-rw-rw-r-- 1 sujata sujata   212441 Apr 10 12:28  image.png
-rw-rw-r-- 1 sujata sujata 14955792 Apr 30 12:01  creation.pdf
-rw-rw-r-- 1 sujata sujata   399313 Apr 16 10:22  kubernetes.pdf
```
To unalias type,
**unalias <your alias name>**
Here its 
```sh
unalias ll
```
15. **clear**: Clears the terminal
```sh
$ clear
``` 
Shortcut is **Ctrl+L**

### Other Useful commands for clearing the screen are : 
- The **clear -x** command clears the terminal but keeps the scrollback buffer, allowing you to scroll up and view previous outputs.
```sh
clear -x
```
- The **reset** command not only clears the terminal but also reinitializes it, restoring default settings.
```sh
reset
```
- Creating an Alias
To avoid typing long commands, you can create an alias for clearing the terminal.
```sh
alias x='printf "\033c"'
```
Now, running x will clear the terminal screen.

# File Management Commands

## 1. Viewing Files and Directories

# `ls` Command in Linux (Ubuntu)

The `ls` command is used to list the contents of directories in Linux systems. It is one of the most frequently used commands for file management.

---

## 🔧 Syntax

```bash
ls [options] [directory]
```

---

## 📁 Basic Usage

### 1. List files in the current directory
```bash
ls
```

**Output Example:**
```text
file1.txt  file2.log  folder1  script.sh
```

### 2. Long listing format (detailed view)
```bash
ls -l
```

**Output Example:**
```text
-rw-r--r-- 1 sujata sujata  1234 May 14 10:23 file1.txt
drwxr-xr-x 2 sujata sujata  4096 May 14 10:25 folder1
```

### 3. Show hidden files
```bash
ls -a
```

**Output Example:**
```text
.  ..  .bashrc  file1.txt  folder1
```

### 4. Long listing with hidden files
```bash
ls -la
```

**Output Example:**
```text
drwxr-xr-x 5 sujata sujata 4096 May 14 10:30 .
-rw-r--r-- 1 sujata sujata  220 May 14 10:10 .bashrc
-rw-r--r-- 1 sujata sujata 1234 May 14 10:23 file1.txt
```

### 5. Human-readable file sizes
```bash
ls -lh
```

**Output Example:**
```text
-rw-r--r-- 1 user user 1.2K May 14 10:23 file1.txt
```

### 6. List files recursively
```bash
ls -R
```

**Output Example:**
```text
.:
file1.txt  folder1

./folder1:
file2.txt
```

---

## 🧩 Commonly Used Options

| Option | Description |
|--------|-------------|
| `-l`   | Use a long listing format |
| `-a`   | Show hidden files |
| `-h`   | Human-readable file sizes |
| `-R`   | List subdirectories recursively |
| `-S`   | Sort files by size |
| `-t`   | Sort by modification time |
| `-r`   | Reverse sort order |

---


## ✅ Example Combining Multiple Options

```bash
ls -alh
```

**Output Example:**
```text
drwxr-xr-x 5 user user 4.0K May 14 10:30 .
-rw-r--r-- 1 user user 1.2K May 14 10:23 file1.txt
-rw-r--r-- 1 user user  220 May 14 10:10 .bashrc
```

---
# `pwd` Command in Linux

The `pwd` command stands for **Print Working Directory**. It displays the full absolute path of the current directory you are in.

---

## ✅ Basic Usage

### 1. Print current directory

```bash
pwd
```

**Example Output:**
```text
/home/sujata/Documents/projects
```

---

## 🧩 Common Options

| Option   | Description                                 |
|----------|---------------------------------------------|
| `-L`     | Use the **logical** path (default)          |
| `-P`     | Use the **physical** path (resolves symlinks) |

---

## 🧪 Examples

### 1. Logical path (default behavior)

```bash
pwd -L
```

**Output Example:**
```text
/home/sujata/symlink-to-projects
```

### 2. Physical path (resolves symlinks)

```bash
pwd -P
```

**Output Example:**
```text
/home/sujata/Documents/projects
```

---
# `tree` Command in Linux

The `tree` command is used to display the directory structure of a path or the whole file system in a tree-like format.

---

## 📌 Common Options

| Option       | Description                                      |
|--------------|--------------------------------------------------|
| `-L n`       | Limits the display to `n` directory levels       |
| `-d`         | Lists directories only                           |
| `-a`         | Includes hidden files                            |
| `-f`         | Prints full path prefix for each file            |
| `--noreport` | Omits the file/directory count at the end        |
| `-h`         | Prints file sizes in human-readable format       |

---

## 📚 Examples

```bash
tree
```
> Displays the tree structure of the current directory.

```bash
tree -L 2
```
> Shows directory contents up to 2 levels deep.

```bash
tree -d
```
> Displays directories only.

```bash
tree -a
```
> Includes hidden files (those starting with `.`).

```bash
tree /path/to/directory
```
> Displays the structure of a specific directory.

---

## ✅ Use Cases

- Visualizing directory structures.
- Creating directory reports for documentation.
- Debugging nested folders in development.
- Listing all files including hidden ones for audits.
- Printing directory tree in scripts or markdown documentation.

---

## 📝 Example Output

```bash
$ tree -L 2

.
├── Documents
│   ├── Resume.pdf
│   └── Report.docx
├── Downloads
│   └── movie.mp4
└── Pictures
    ├── beach.png
    └── family.jpg
```

> You can redirect this output to a file for documentation:

```bash
tree -L 2 > directory_structure.txt
```

## 2. Creating Files and Directories

- `touch <filename>`  
  Create a new empty file.  
  **Example:** 
```sh
touch file.txt
```
- `mkdir <dirname>`  
  Create a new directory.  
  **Example:** 
```sh
mkdir my_folder
```
- `mkdir -p <parent>/<child>`  
  Create nested directories.  
  **Example:** 
```sh
mkdir -p projects/java
```
## 3. Copying Files and Directories

- `cp <source> <destination>`  
  Copy a file.  
  **Example:** 
```sh
cp file.txt backup.txt
```
- `cp -r <source_dir> <destination_dir>`  
  Copy directories recursively.  
  **Example:** 
```sh
cp -r docs/ backup_docs/
```
## 4. Moving and Renaming Files

- `mv <source> <destination>`  
  Move or rename files/directories.  
  **Example:** 
```sh
mv oldname.txt newname.txt
mv file.txt /home/sujata/Documents/
```
## 5. Deleting Files and Directories

- `rm <filename>`  
  Delete a file.  
  **Example:** 
```sh
rm file.txt
```
- `rm -r <dirname>`  
  Delete a directory and its contents recursively.  
  **Example:** 
```sh
rm -r my_folder/
```
- `rm -rf <dirname>`  
  Force delete directory without prompting. **(Use with caution)**  
  **Example:** 
```sh
rm -rf /tmp/test/
```
Force delete directory without prompting.
- `rmdir <directories names>`
Remove multiple directories:
```sh
 rmdir dir1 dir2 dir3
```
## 6. Viewing File Contents

- `cat <filename>`  
  Display file content.  
  **Example:** 
```sh
cat file.txt
```
- `less <filename>`  
  View file content one page at a time.  
  **Example:** 
```sh
less file.txt
```
- `head <filename>`  
  Show the first 10 lines of a file.  
  **Example:** 
```sh
head file.txt
```
- `tail <filename>`  
  Show the last 10 lines of a file.  
  **Example:** 
```sh
tail file.txt
```
## 7. Finding Files and Directories

- `find <path> -name <pattern>`  
  Search for files and directories.  
  **Example:** 
```sh
find /home -name "*.txt"
```
- `locate <filename>`  
  Quickly find files (requires updated database with `updatedb`).  
  **Example:** 
```sh
locate file.txt
```
## 8. File Permissions and Ownership

- `chmod <permissions> <filename>`  
  Change file permissions.  
  **Example:** 
```sh
chmod 755 script.sh
```
- `chown <user>:<group> <filename>`  
  Change file owner and group.  
  **Example:** 
```sh
chown sujata:staff file.txt
```
## 9. Disk Usage and Space

- Display disk space usage in human-readable format.
```sh
df -h
```
- Show size of a directory.
```sh
du -sh <directory>
```
---





