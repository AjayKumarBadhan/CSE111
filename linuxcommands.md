# Linux Basic Commands Reference Guide

## Table of Contents
1. [File and Directory Operations](#file-and-directory-operations)
2. [File Content Operations](#file-content-operations)
3. [File Permissions and Ownership](#file-permissions-and-ownership)
4. [Process Management](#process-management)
5. [System Information](#system-information)
6. [Network Commands](#network-commands)
7. [Archive and Compression](#archive-and-compression)
8. [Text Processing](#text-processing)
9. [Search and Find](#search-and-find)
10. [System Control](#system-control)

---

## File and Directory Operations

### `ls` - List Directory Contents
**Definition:** Lists files and directories in the current or specified directory.

**Syntax:** `ls [options] [directory]`

**Examples:**
```bash
ls                    # List current directory
ls -l                 # Long format listing
ls -la                # Include hidden files in long format
ls -lh                # Human-readable file sizes
ls -lt                # Sort by modification time
ls -lS                # Sort by file size
ls -R                 # Recursive listing
ls /home/user         # List specific directory
ls *.txt              # List all .txt files
ls -ld */             # List only directories
```

### `cd` - Change Directory
**Definition:** Changes the current working directory.

**Syntax:** `cd [directory]`

**Examples:**
```bash
cd                    # Go to home directory
cd ~                  # Go to home directory
cd /                  # Go to root directory
cd ..                 # Go up one directory
cd ../..              # Go up two directories
cd -                  # Go to previous directory
cd /home/user/docs    # Go to specific directory
cd ~/Documents        # Go to Documents in home
```

### `pwd` - Print Working Directory
**Definition:** Displays the current working directory path.

**Syntax:** `pwd [options]`

**Examples:**
```bash
pwd                   # Show current directory
pwd -L                # Show logical path (default)
pwd -P                # Show physical path (resolve symlinks)
```

### `mkdir` - Make Directory
**Definition:** Creates directories.

**Syntax:** `mkdir [options] directory_name`

**Examples:**
```bash
mkdir mydir           # Create single directory
mkdir dir1 dir2 dir3  # Create multiple directories
mkdir -p path/to/dir  # Create parent directories if needed
mkdir -m 755 mydir    # Create with specific permissions
mkdir -v mydir        # Verbose output
mkdir -p ~/projects/{web,mobile,desktop}  # Create nested structure
```

### `rmdir` - Remove Empty Directory
**Definition:** Removes empty directories.

**Syntax:** `rmdir [options] directory_name`

**Examples:**
```bash
rmdir mydir           # Remove empty directory
rmdir -v mydir        # Verbose removal
rmdir -p path/to/dir  # Remove directory and empty parents
rmdir dir1 dir2       # Remove multiple empty directories
```

### `rm` - Remove Files and Directories
**Definition:** Deletes files and directories.

**Syntax:** `rm [options] file/directory`

**Examples:**
```bash
rm file.txt           # Remove file
rm -i file.txt        # Interactive removal (ask confirmation)
rm -f file.txt        # Force removal (no prompts)
rm -r directory       # Remove directory recursively
rm -rf directory      # Force recursive removal
rm -v file.txt        # Verbose removal
rm *.tmp              # Remove all .tmp files
rm -rf /path/to/dir   # Dangerous: force remove directory tree
```

### `cp` - Copy Files and Directories
**Definition:** Copies files and directories.

**Syntax:** `cp [options] source destination`

**Examples:**
```bash
cp file1.txt file2.txt        # Copy file
cp -i file1.txt file2.txt     # Interactive copy (ask before overwrite)
cp -r dir1 dir2               # Copy directory recursively
cp -p file1.txt file2.txt     # Preserve attributes
cp -u file1.txt file2.txt     # Copy only if source is newer
cp -v file1.txt file2.txt     # Verbose copy
cp file.txt ~/backup/         # Copy to directory
cp *.txt backup/              # Copy all .txt files
cp -a dir1 dir2               # Archive copy (preserve all)
```

### `mv` - Move/Rename Files and Directories
**Definition:** Moves or renames files and directories.

**Syntax:** `mv [options] source destination`

**Examples:**
```bash
mv file1.txt file2.txt        # Rename file
mv file.txt /home/user/       # Move file to directory
mv -i file1.txt file2.txt     # Interactive move
mv -u file1.txt file2.txt     # Move only if source is newer
mv -v file1.txt file2.txt     # Verbose move
mv dir1 dir2                  # Rename directory
mv *.txt documents/           # Move all .txt files
```

---

## File Content Operations

### `cat` - Display File Content
**Definition:** Displays the content of files.

**Syntax:** `cat [options] file`

**Examples:**
```bash
cat file.txt                  # Display file content
cat file1.txt file2.txt       # Display multiple files
cat -n file.txt               # Show line numbers
cat -b file.txt               # Number non-blank lines
cat -s file.txt               # Squeeze blank lines
cat -A file.txt               # Show all characters (including hidden)
cat > newfile.txt             # Create file (Ctrl+D to save)
cat file1.txt > file2.txt     # Copy file content
```

### `less` - View File Content Page by Page
**Definition:** Views file content one page at a time.

**Syntax:** `less [options] file`

**Examples:**
```bash
less file.txt                 # View file
less +F file.txt              # Follow file (like tail -f)
less +G file.txt              # Start at end of file
less -N file.txt              # Show line numbers
less -S file.txt              # Don't wrap long lines
less +/pattern file.txt       # Start at first match of pattern
```

### `more` - View File Content Page by Page
**Definition:** Views file content one page at a time (simpler than less).

**Syntax:** `more [options] file`

**Examples:**
```bash
more file.txt                 # View file
more +10 file.txt             # Start at line 10
more -s file.txt              # Squeeze blank lines
```

### `head` - Display First Lines of File
**Definition:** Shows the first lines of a file.

**Syntax:** `head [options] file`

**Examples:**
```bash
head file.txt                 # Show first 10 lines
head -n 20 file.txt           # Show first 20 lines
head -5 file.txt              # Show first 5 lines
head -c 100 file.txt          # Show first 100 characters
head -v file.txt              # Verbose (show filename)
head file1.txt file2.txt      # Show first lines of multiple files
```

### `tail` - Display Last Lines of File
**Definition:** Shows the last lines of a file.

**Syntax:** `tail [options] file`

**Examples:**
```bash
tail file.txt                 # Show last 10 lines
tail -n 20 file.txt           # Show last 20 lines
tail -5 file.txt              # Show last 5 lines
tail -f file.txt              # Follow file (monitor for changes)
tail -F file.txt              # Follow file name (even if recreated)
tail -c 100 file.txt          # Show last 100 characters
tail -f /var/log/syslog       # Monitor log file
```

### `touch` - Create Empty Files or Update Timestamps
**Definition:** Creates empty files or updates file timestamps.

**Syntax:** `touch [options] file`

**Examples:**
```bash
touch newfile.txt             # Create empty file
touch file1.txt file2.txt     # Create multiple files
touch -a file.txt             # Update access time only
touch -m file.txt             # Update modification time only
touch -c file.txt             # Don't create file if it doesn't exist
touch -t 202301011200 file.txt # Set specific timestamp
touch -r ref.txt file.txt     # Use reference file's timestamp
```

---

## File Permissions and Ownership

### `chmod` - Change File Permissions
**Definition:** Changes file and directory permissions.

**Syntax:** `chmod [options] permissions file`

**Examples:**
```bash
chmod 755 file.txt            # Set rwxr-xr-x permissions
chmod +x script.sh            # Add execute permission
chmod -w file.txt             # Remove write permission
chmod u+x file.txt            # Add execute for user
chmod g-w file.txt            # Remove write for group
chmod o+r file.txt            # Add read for others
chmod a+x file.txt            # Add execute for all
chmod -R 755 directory        # Recursive permission change
chmod u=rwx,go=rx file.txt    # Set specific permissions
```

### `chown` - Change File Ownership
**Definition:** Changes file and directory ownership.

**Syntax:** `chown [options] owner[:group] file`

**Examples:**
```bash
chown user file.txt           # Change owner
chown user:group file.txt     # Change owner and group
chown :group file.txt         # Change group only
chown -R user:group dir       # Recursive ownership change
chown --reference=ref.txt file.txt # Use reference file
chown -v user file.txt        # Verbose output
```

### `chgrp` - Change Group Ownership
**Definition:** Changes group ownership of files and directories.

**Syntax:** `chgrp [options] group file`

**Examples:**
```bash
chgrp group file.txt          # Change group
chgrp -R group directory      # Recursive group change
chgrp -v group file.txt       # Verbose output
chgrp --reference=ref.txt file.txt # Use reference file
```

### `umask` - Set Default Permissions
**Definition:** Sets default permissions for newly created files.

**Syntax:** `umask [permissions]`

**Examples:**
```bash
umask                         # Show current umask
umask 022                     # Set umask to 022
umask -S                      # Show symbolic representation
umask u=rwx,g=rx,o=rx        # Set symbolic umask
```

---

## Process Management

### `ps` - Display Running Processes
**Definition:** Shows information about running processes.

**Syntax:** `ps [options]`

**Examples:**
```bash
ps                            # Show current user's processes
ps aux                        # Show all processes (detailed)
ps -ef                        # Show all processes (full format)
ps -u username                # Show processes for specific user
ps -p 1234                    # Show specific process by PID
ps axjf                       # Show process tree
ps --sort=-%cpu               # Sort by CPU usage
ps --sort=-%mem               # Sort by memory usage
```

### `top` - Display and Monitor Processes
**Definition:** Displays and continuously updates running processes.

**Syntax:** `top [options]`

**Examples:**
```bash
top                           # Start top
top -u username               # Show processes for specific user
top -p 1234,5678              # Monitor specific PIDs
top -d 5                      # Update every 5 seconds
top -n 10                     # Run for 10 iterations then exit
```

### `htop` - Enhanced Process Viewer
**Definition:** Enhanced version of top with better interface.

**Syntax:** `htop [options]`

**Examples:**
```bash
htop                          # Start htop
htop -u username              # Show processes for specific user
htop -p 1234,5678             # Monitor specific PIDs
htop -d 50                    # Update delay (tenths of seconds)
```

### `kill` - Terminate Processes
**Definition:** Sends signals to processes to terminate them.

**Syntax:** `kill [options] PID`

**Examples:**
```bash
kill 1234                     # Send TERM signal to process
kill -9 1234                  # Send KILL signal (force kill)
kill -STOP 1234               # Stop (pause) process
kill -CONT 1234               # Continue stopped process
kill -l                       # List all available signals
kill -HUP 1234                # Send hangup signal
killall firefox               # Kill all firefox processes
```

### `jobs` - Display Active Jobs
**Definition:** Shows active jobs in the current shell.

**Syntax:** `jobs [options]`

**Examples:**
```bash
jobs                          # List active jobs
jobs -l                       # List with PID numbers
jobs -p                       # List PID numbers only
jobs -r                       # List running jobs only
jobs -s                       # List stopped jobs only
```

### `bg` - Put Jobs in Background
**Definition:** Puts jobs in the background.

**Syntax:** `bg [job_id]`

**Examples:**
```bash
bg                            # Put current job in background
bg %1                         # Put job 1 in background
bg %+                         # Put most recent job in background
```

### `fg` - Bring Jobs to Foreground
**Definition:** Brings jobs to the foreground.

**Syntax:** `fg [job_id]`

**Examples:**
```bash
fg                            # Bring current job to foreground
fg %1                         # Bring job 1 to foreground
fg %-                         # Bring previous job to foreground
```

### `nohup` - Run Commands Immune to Hangups
**Definition:** Runs commands that continue after logout.

**Syntax:** `nohup command [arguments]`

**Examples:**
```bash
nohup ./script.sh             # Run script immune to hangup
nohup ./script.sh &           # Run in background
nohup python app.py > output.log 2>&1 & # Redirect output
```

---

## System Information

### `uname` - System Information
**Definition:** Displays system information.

**Syntax:** `uname [options]`

**Examples:**
```bash
uname                         # Show kernel name
uname -a                      # Show all information
uname -s                      # Show kernel name
uname -r                      # Show kernel release
uname -v                      # Show kernel version
uname -m                      # Show machine hardware
uname -p                      # Show processor type
uname -o                      # Show operating system
```

### `whoami` - Current Username
**Definition:** Displays the current username.

**Syntax:** `whoami`

**Examples:**
```bash
whoami                        # Show current username
```

### `who` - Logged in Users
**Definition:** Shows who is logged into the system.

**Syntax:** `who [options]`

**Examples:**
```bash
who                           # Show logged in users
who -a                        # Show all information
who -b                        # Show boot time
who -q                        # Show user count
who -u                        # Show idle time
who am i                      # Show current user info
```

### `w` - Show Logged in Users and Activity
**Definition:** Shows logged in users and their activity.

**Syntax:** `w [options] [user]`

**Examples:**
```bash
w                             # Show all users and activity
w username                    # Show specific user activity
w -h                          # Don't show header
w -s                          # Short format
```

### `id` - User and Group IDs
**Definition:** Shows user and group IDs.

**Syntax:** `id [options] [user]`

**Examples:**
```bash
id                            # Show current user's IDs
id username                   # Show specific user's IDs
id -u                         # Show user ID only
id -g                         # Show group ID only
id -G                         # Show all group IDs
id -n -u                      # Show username
```

### `date` - Display or Set Date
**Definition:** Displays or sets the system date.

**Syntax:** `date [options] [format]`

**Examples:**
```bash
date                          # Show current date and time
date +"%Y-%m-%d"             # Show date in YYYY-MM-DD format
date +"%H:%M:%S"             # Show time in HH:MM:SS format
date +"%A, %B %d, %Y"        # Show full date format
date -d "tomorrow"           # Show tomorrow's date
date -d "2 days ago"         # Show date 2 days ago
date -s "2023-12-25 10:30:00" # Set date and time
```

### `uptime` - System Uptime
**Definition:** Shows how long the system has been running.

**Syntax:** `uptime [options]`

**Examples:**
```bash
uptime                        # Show uptime and load
uptime -p                     # Show uptime in pretty format
uptime -s                     # Show boot time
```

### `df` - Display Filesystem Usage
**Definition:** Shows filesystem disk space usage.

**Syntax:** `df [options] [filesystem]`

**Examples:**
```bash
df                            # Show all filesystems
df -h                         # Human readable format
df -T                         # Show filesystem type
df -i                         # Show inode usage
df /home                      # Show specific filesystem
df -x tmpfs                   # Exclude filesystem type
```

### `du` - Display Directory Usage
**Definition:** Shows directory disk usage.

**Syntax:** `du [options] [directory]`

**Examples:**
```bash
du                            # Show current directory usage
du -h                         # Human readable format
du -s                         # Summary (total only)
du -a                         # Show all files
du -d 1                       # Limit depth to 1 level
du --max-depth=2             # Limit depth to 2 levels
du -sh /home/user            # Show summary of specific directory
```

### `free` - Display Memory Usage
**Definition:** Shows memory usage information.

**Syntax:** `free [options]`

**Examples:**
```bash
free                          # Show memory usage
free -h                       # Human readable format
free -m                       # Show in MB
free -g                       # Show in GB
free -s 5                     # Update every 5 seconds
free -t                       # Show totals
```

---

## Network Commands

### `ping` - Test Network Connectivity
**Definition:** Tests network connectivity to a host.

**Syntax:** `ping [options] host`

**Examples:**
```bash
ping google.com               # Ping google.com
ping -c 4 google.com          # Ping 4 times
ping -i 2 google.com          # Ping every 2 seconds
ping -s 1000 google.com       # Set packet size to 1000 bytes
ping -W 5 google.com          # Set timeout to 5 seconds
ping -f google.com            # Flood ping (root only)
```

### `wget` - Download Files from Web
**Definition:** Downloads files from web servers.

**Syntax:** `wget [options] URL`

**Examples:**
```bash
wget http://example.com/file.zip     # Download file
wget -O newname.zip http://example.com/file.zip # Save with different name
wget -c http://example.com/file.zip  # Continue partial download
wget -r http://example.com/          # Recursive download
wget --limit-rate=100k http://example.com/file.zip # Limit download speed
wget -b http://example.com/file.zip  # Download in background
```

### `curl` - Transfer Data from Servers
**Definition:** Transfers data from or to servers.

**Syntax:** `curl [options] URL`

**Examples:**
```bash
curl http://example.com              # Display webpage content
curl -O http://example.com/file.zip  # Download file
curl -o newname.zip http://example.com/file.zip # Save with different name
curl -I http://example.com           # Show headers only
curl -L http://example.com           # Follow redirects
curl -u user:pass http://example.com # Use authentication
curl -X POST http://example.com/api  # Send POST request
```

### `ssh` - Secure Shell Remote Login
**Definition:** Connects to remote systems securely.

**Syntax:** `ssh [options] user@host`

**Examples:**
```bash
ssh user@server.com               # Connect to remote server
ssh -p 2222 user@server.com       # Connect on specific port
ssh -i ~/.ssh/mykey user@server.com # Use specific key
ssh -X user@server.com            # Enable X11 forwarding
ssh -L 8080:localhost:80 user@server.com # Local port forwarding
ssh -v user@server.com            # Verbose connection
```

### `scp` - Secure Copy over Network
**Definition:** Copies files securely over network.

**Syntax:** `scp [options] source destination`

**Examples:**
```bash
scp file.txt user@server.com:/home/user/ # Copy file to remote
scp user@server.com:/path/file.txt .     # Copy file from remote
scp -r directory user@server.com:/home/  # Copy directory recursively
scp -P 2222 file.txt user@server.com:/   # Use specific port
scp -i ~/.ssh/mykey file.txt user@server.com:/ # Use specific key
```

---

## Archive and Compression

### `tar` - Archive Files
**Definition:** Creates and extracts archive files.

**Syntax:** `tar [options] archive_name files`

**Examples:**
```bash
tar -cvf archive.tar file1 file2     # Create archive
tar -xvf archive.tar                 # Extract archive
tar -tvf archive.tar                 # List archive contents
tar -czvf archive.tar.gz directory   # Create compressed archive
tar -xzvf archive.tar.gz             # Extract compressed archive
tar -cjvf archive.tar.bz2 directory  # Create bzip2 compressed archive
tar -xjvf archive.tar.bz2            # Extract bzip2 compressed archive
tar --exclude='*.log' -czf backup.tar.gz /home/user # Exclude files
```

### `gzip` - Compress Files
**Definition:** Compresses files using gzip compression.

**Syntax:** `gzip [options] file`

**Examples:**
```bash
gzip file.txt                        # Compress file
gzip -d file.txt.gz                  # Decompress file
gzip -c file.txt > file.txt.gz       # Keep original file
gzip -r directory                    # Compress all files in directory
gzip -9 file.txt                     # Maximum compression
gzip -1 file.txt                     # Fastest compression
```

### `gunzip` - Decompress gzip Files
**Definition:** Decompresses gzip compressed files.

**Syntax:** `gunzip [options] file.gz`

**Examples:**
```bash
gunzip file.txt.gz                   # Decompress file
gunzip -c file.txt.gz > file.txt     # Keep compressed file
gunzip -t file.txt.gz                # Test compressed file
```

### `zip` - Create ZIP Archives
**Definition:** Creates ZIP format archives.

**Syntax:** `zip [options] archive.zip files`

**Examples:**
```bash
zip archive.zip file1 file2          # Create zip archive
zip -r archive.zip directory         # Recursively zip directory
zip -e archive.zip file.txt          # Create encrypted zip
zip -9 archive.zip file.txt          # Maximum compression
zip -j archive.zip path/to/file.txt  # Don't store directory structure
```

### `unzip` - Extract ZIP Archives
**Definition:** Extracts ZIP format archives.

**Syntax:** `unzip [options] archive.zip`

**Examples:**
```bash
unzip archive.zip                    # Extract zip archive
unzip -l archive.zip                 # List archive contents
unzip -t archive.zip                 # Test archive integrity
unzip -d /path/to/extract archive.zip # Extract to specific directory
unzip -j archive.zip                 # Extract without directory structure
unzip -o archive.zip                 # Overwrite files without asking
```

---

## Text Processing

### `grep` - Search Text Patterns
**Definition:** Searches for patterns in text files.

**Syntax:** `grep [options] pattern file`

**Examples:**
```bash
grep "pattern" file.txt              # Search for pattern
grep -i "pattern" file.txt           # Case insensitive search
grep -v "pattern" file.txt           # Invert match (exclude lines)
grep -n "pattern" file.txt           # Show line numbers
grep -r "pattern" directory          # Recursive search
grep -l "pattern" *.txt              # Show only filenames
grep -c "pattern" file.txt           # Count matches
grep -A 3 "pattern" file.txt         # Show 3 lines after match
grep -B 3 "pattern" file.txt         # Show 3 lines before match
grep -C 3 "pattern" file.txt         # Show 3 lines before and after
grep "^start" file.txt               # Lines starting with "start"
grep "end$" file.txt                 # Lines ending with "end"
```

### `sed` - Stream Editor
**Definition:** Stream editor for filtering and transforming text.

**Syntax:** `sed [options] 'command' file`

**Examples:**
```bash
sed 's/old/new/' file.txt            # Replace first occurrence per line
sed 's/old/new/g' file.txt           # Replace all occurrences
sed 's/old/new/gi' file.txt          # Case insensitive replacement
sed -n '5p' file.txt                 # Print line 5
sed -n '1,10p' file.txt              # Print lines 1-10
sed '5d' file.txt                    # Delete line 5
sed '/pattern/d' file.txt            # Delete lines containing pattern
sed -i 's/old/new/g' file.txt        # Edit file in place
sed 's/^/> /' file.txt               # Add "> " to beginning of each line
```

### `awk` - Pattern Scanning and Processing
**Definition:** Pattern scanning and data extraction tool.

**Syntax:** `awk 'pattern { action }' file`

**Examples:**
```bash
awk '{print $1}' file.txt            # Print first column
awk '{print $NF}' file.txt           # Print last column
awk '{print NR, $0}' file.txt        # Add line numbers
awk '/pattern/ {print}' file.txt     # Print lines matching pattern
awk '{sum += $1} END {print sum}' file.txt # Sum first column
awk -F: '{print $1}' /etc/passwd     # Use : as field separator
awk 'length > 80' file.txt           # Print lines longer than 80 chars
awk '{print $2, $1}' file.txt        # Swap first two columns
```

### `sort` - Sort Lines
**Definition:** Sorts lines in text files.

**Syntax:** `sort [options] file`

**Examples:**
```bash
sort file.txt                        # Sort alphabetically
sort -n file.txt                     # Sort numerically
sort -r file.txt                     # Reverse sort
sort -u file.txt                     # Sort and remove duplicates
sort -k 2 file.txt                   # Sort by second column
sort -t: -k 3 -n /etc/passwd         # Sort by 3rd field using : separator
sort -f file.txt                     # Case insensitive sort
sort -M file.txt                     # Sort by month names
```

### `uniq` - Remove Duplicate Lines
**Definition:** Removes or reports duplicate lines.

**Syntax:** `uniq [options] file`

**Examples:**
```bash
uniq file.txt                        # Remove consecutive duplicates
uniq -d file.txt                     # Show only duplicate lines
uniq -u file.txt                     # Show only unique lines
uniq -c file.txt                     # Count occurrences
uniq -i file.txt                     # Case insensitive comparison
sort file.txt | uniq                 # Remove all duplicates
```

### `wc` - Word, Line, Character Count
**Definition:** Counts words, lines, and characters in files.

**Syntax:** `wc [options] file`

**Examples:**
```bash
wc file.txt                          # Show lines, words, characters
wc -l file.txt                       # Count lines only
wc -w file.txt                       # Count words only
wc -c file.txt                       # Count characters only
wc -m file.txt                       # Count characters (multibyte aware)
wc *.txt                             # Count for multiple files
```

### `cut` - Extract Columns
**Definition:** Extracts columns from text files.

**Syntax:** `cut [options] file`

**Examples:**
```bash
cut -c 1-10 file.txt                 # Extract characters 1-10
cut -f 1,3 file.txt                  # Extract fields 1 and 3
cut -d: -f 1 /etc/passwd             # Use : as delimiter, extract field 1
cut -d, -f 2- file.csv               # Extract from field 2 to end
cut -c 5- file.txt                   # Extract from character 5 to end
```

### `tr` - Translate Characters
**Definition:** Translates or deletes characters.

**Syntax:** `tr [options] set1 [set2]`

**Examples:**
```bash
tr 'a-z' 'A-Z' < file.txt            # Convert to uppercase
tr -d ' ' < file.txt                 # Delete spaces
tr -s ' ' < file.txt                 # Squeeze multiple spaces to one
tr '\n' ' ' < file.txt               # Replace newlines with spaces
tr -cd '0-9\n' < file.txt            # Keep only digits and newlines
echo "hello" | tr 'l' 'L'            # Replace specific characters
```

---

## Search and Find

### `find` - Find Files and Directories
**Definition:** Searches for files and directories.

**Syntax:** `find [path] [options] [tests] [actions]`

**Examples:**
```bash
find . -name "*.txt"                 # Find .txt files in current directory
find /home -user username            # Find files owned by user
find . -type f -size +100M           # Find files larger than 100MB
find . -type d -name "temp*"         # Find directories starting with "temp"
find . -mtime -7                     # Find files modified in last 7 days
find . -perm 755                     # Find files with specific permissions
find . -name "*.log" -delete         # Find and delete .log files
find . -name "*.txt" -exec grep "pattern" {} \; # Execute command on found files
find . -empty                        # Find empty files and directories
find . -type f -executable           # Find executable files
```

### `locate` - Find Files by Name
**Definition:** Finds files by name using a database.

**Syntax:** `locate [options] pattern`

**Examples:**
```bash
locate filename.txt                  # Find file by name
locate -i filename.txt               # Case insensitive search
locate -c "*.pdf"                    # Count matching files
locate -r "\.txt$"                   # Use regex pattern
updatedb                             # Update locate database (as root)
```

### `which` - Locate Command
**Definition:** Shows the path of commands.

**Syntax:** `which command`

**Examples:**
```bash
which python                         # Show path to python
which -a python                      # Show all paths to python
which ls grep cat                    # Show paths to multiple commands
```

### `whereis` - Locate Binary, Source, Manual
**Definition:** Locates binary, source, and manual page files.

**Syntax:** `whereis [options] command`

**Examples:**
```bash
whereis ls                           # Find ls binary, source, manual
whereis -b ls                        # Find binary only
whereis -m ls                        # Find manual only
whereis -s gcc                       # Find source only
```

---

## System Control

### `sudo` - Execute as Another User
**Definition:** Executes commands as another user (typically root).

**Syntax:** `sudo [options] command`

**Examples:**
```bash
sudo command                         # Run command as root
sudo -u username command             # Run command as specific user
sudo -i                              # Start interactive root shell
sudo -s                              # Start shell
sudo -l                              # List allowed commands
sudo -k                              # Invalidate cached credentials
sudo !! 				     # Run previous command with sudo
```

### `su` - Switch User
**Definition:** Switches to another user account.

**Syntax:** `su [options] [username]`

**Examples:**
```bash
su                                   # Switch to root
su username                          # Switch to specific user
su -                                 # Switch to root with environment
su - username                        # Switch to user with environment
su -c "command" username             # Run single command as user
su -s /bin/bash username             # Use specific shell
```

### `passwd` - Change Password
**Definition:** Changes user passwords.

**Syntax:** `passwd [options] [username]`

**Examples:**
```bash
passwd                               # Change current user's password
passwd username                      # Change another user's password (root)
passwd -l username                   # Lock user account
passwd -u username                   # Unlock user account
passwd -d username                   # Delete password (make passwordless)
passwd -S username                   # Show password status
```

### `history` - Command History
**Definition:** Shows command history.

**Syntax:** `history [options]`

**Examples:**
```bash
history                              # Show command history
history 10                           # Show last 10 commands
history -c                           # Clear history
history -d 5                         # Delete command 5 from history
!100                                 # Execute command 100 from history
!!                                   # Execute previous command
!grep                                # Execute last command starting with "grep"
```

### `alias` - Create Command Aliases
**Definition:** Creates aliases for commands.

**Syntax:** `alias [name='command']`

**Examples:**
```bash
alias                                # Show all aliases
alias ll='ls -la'                    # Create alias for long listing
alias grep='grep --color=auto'       # Add color to grep
alias ..='cd ..'                     # Shortcut to go up directory
alias la='ls -la'                    # Another listing alias
unalias ll                           # Remove alias
```

### `export` - Set Environment Variables
**Definition:** Sets environment variables.

**Syntax:** `export [variable=value]`

**Examples:**
```bash
export PATH=$PATH:/new/path          # Add directory to PATH
export EDITOR=vim                    # Set default editor
export JAVA_HOME=/usr/lib/jvm/java   # Set Java home directory
export -p                            # Show all exported variables
export LC_ALL=C                      # Set locale
unset VARIABLE                       # Remove environment variable
```

### `env` - Display Environment Variables
**Definition:** Displays or modifies environment variables.

**Syntax:** `env [options] [variable=value] [command]`

**Examples:**
```bash
env                                  # Show all environment variables
env | grep PATH                      # Show PATH variable
env -u HOME command                  # Run command without HOME variable
env PATH=/bin:/usr/bin command       # Run command with modified PATH
env -i command                       # Run command with empty environment
```

### `printenv` - Print Environment Variables
**Definition:** Prints environment variables.

**Syntax:** `printenv [variable]`

**Examples:**
```bash
printenv                             # Print all environment variables
printenv HOME                        # Print HOME variable
printenv PATH USER                   # Print multiple variables
```

### `crontab` - Schedule Tasks
**Definition:** Manages scheduled tasks (cron jobs).

**Syntax:** `crontab [options]`

**Examples:**
```bash
crontab -l                           # List cron jobs
crontab -e                           # Edit cron jobs
crontab -r                           # Remove all cron jobs
crontab -u username -l               # List jobs for specific user
crontab myfile                       # Install cron jobs from file
```

### `systemctl` - Control systemd Services
**Definition:** Controls systemd services and units.

**Syntax:** `systemctl [options] command [unit]`

**Examples:**
```bash
systemctl status service             # Show service status
systemctl start service              # Start service
systemctl stop service               # Stop service
systemctl restart service            # Restart service
systemctl enable service             # Enable service at boot
systemctl disable service            # Disable service at boot
systemctl list-units                 # List all units
systemctl daemon-reload              # Reload systemd configuration
```

### `service` - Control System Services
**Definition:** Controls system services (SysV init).

**Syntax:** `service service_name command`

**Examples:**
```bash
service apache2 status               # Check service status
service apache2 start                # Start service
service apache2 stop                 # Stop service
service apache2 restart              # Restart service
service --status-all                 # Show status of all services
```

---

## Input/Output Redirection

### Redirection Operators
**Definition:** Redirects input and output of commands.

**Examples:**
```bash
command > file.txt                   # Redirect stdout to file (overwrite)
command >> file.txt                  # Redirect stdout to file (append)
command < file.txt                   # Redirect stdin from file
command 2> error.log                 # Redirect stderr to file
command &> output.log                # Redirect both stdout and stderr
command 2>&1                         # Redirect stderr to stdout
command | another_command            # Pipe output to another command
command1 && command2                 # Run command2 if command1 succeeds
command1 || command2                 # Run command2 if command1 fails
command1 ; command2                  # Run commands sequentially
command &                            # Run command in background
```

### `tee` - Write Output to File and stdout
**Definition:** Writes output to both file and standard output.

**Syntax:** `tee [options] file`

**Examples:**
```bash
command | tee output.txt             # Save output to file and display
command | tee -a output.txt          # Append to file and display
command | tee file1.txt file2.txt    # Write to multiple files
ls -la | tee directory_listing.txt   # Example usage
```

---

## File Comparison

### `diff` - Compare Files
**Definition:** Compares files line by line.

**Syntax:** `diff [options] file1 file2`

**Examples:**
```bash
diff file1.txt file2.txt             # Compare two files
diff -u file1.txt file2.txt          # Unified diff format
diff -c file1.txt file2.txt          # Context diff format
diff -y file1.txt file2.txt          # Side-by-side comparison
diff -r dir1 dir2                    # Compare directories recursively
diff -i file1.txt file2.txt          # Case insensitive comparison
diff -w file1.txt file2.txt          # Ignore whitespace differences
```

### `cmp` - Compare Files Byte by Byte
**Definition:** Compares files byte by byte.

**Syntax:** `cmp [options] file1 file2`

**Examples:**
```bash
cmp file1.txt file2.txt              # Compare files
cmp -l file1.txt file2.txt           # Show all differences
cmp -s file1.txt file2.txt           # Silent mode (exit code only)
```

---

## Archive Information

### `file` - Determine File Type
**Definition:** Determines file type based on content.

**Syntax:** `file [options] file`

**Examples:**
```bash
file document.pdf                    # Determine file type
file -b document.pdf                 # Brief output (no filename)
file -i document.pdf                 # Show MIME type
file *                               # Check all files in directory
file -z compressed.gz                # Look inside compressed files
```

### `stat` - Display File Statistics
**Definition:** Displays detailed file statistics.

**Syntax:** `stat [options] file`

**Examples:**
```bash
stat file.txt                        # Show file statistics
stat -c %s file.txt                  # Show file size only
stat -c %a file.txt                  # Show permissions in octal
stat -c %U file.txt                  # Show owner name
stat -c %G file.txt                  # Show group name
stat -f /                            # Show filesystem statistics
```

---

## Monitoring and Performance

### `iostat` - I/O Statistics
**Definition:** Reports I/O statistics for devices and partitions.

**Syntax:** `iostat [options] [interval] [count]`

**Examples:**
```bash
iostat                               # Show I/O statistics
iostat -x                            # Extended statistics
iostat 2                             # Update every 2 seconds
iostat -d 2 5                        # Show disk stats, 2 sec intervals, 5 times
```

### `vmstat` - Virtual Memory Statistics
**Definition:** Reports virtual memory statistics.

**Syntax:** `vmstat [options] [interval] [count]`

**Examples:**
```bash
vmstat                               # Show VM statistics
vmstat 2                             # Update every 2 seconds
vmstat 2 5                           # 2 second intervals, 5 times
vmstat -d                            # Show disk statistics
vmstat -s                            # Show memory statistics
```

### `sar` - System Activity Reporter
**Definition:** Collects and reports system activity information.

**Syntax:** `sar [options] [interval] [count]`

**Examples:**
```bash
sar                                  # Show CPU utilization
sar -u 2 5                           # CPU stats, 2 sec intervals, 5 times
sar -r                               # Memory utilization
sar -d                               # Disk activity
sar -n DEV                           # Network statistics
```

---

## Quick Reference Summary

### Most Essential Commands for Daily Use:
1. **Navigation**: `cd`, `pwd`, `ls`
2. **File Operations**: `cp`, `mv`, `rm`, `mkdir`
3. **File Viewing**: `cat`, `less`, `head`, `tail`
4. **Text Processing**: `grep`, `sed`, `awk`
5. **Permissions**: `chmod`, `chown`
6. **Process Management**: `ps`, `top`, `kill`
7. **System Info**: `df`, `free`, `uname`
8. **Search**: `find`, `locate`
9. **Archives**: `tar`, `zip`, `unzip`
10. **Help**: `man`, `help`, `--help`

### Keyboard Shortcuts:
- `Ctrl+C`: Interrupt/Cancel command
- `Ctrl+Z`: Suspend command
- `Ctrl+D`: End of input/Exit
- `Ctrl+L`: Clear screen
- `Ctrl+R`: Reverse search history
- `Tab`: Auto-complete
- `!!`: Previous command
- `!# Linux Basic Commands Reference Guide

## Table of Contents
1. [File and Directory Operations](#file-and-directory-operations)
2. [File Content Operations](#file-content-operations)
3. [File Permissions and Ownership](#file-permissions-and-ownership)
4. [Process Management](#process-management)
5. [System Information](#system-information)
6. [Network Commands](#network-commands)
7. [Archive and Compression](#archive-and-compression)
8. [Text Processing](#text-processing)
9. [Search and Find](#search-and-find)
10. [System Control](#system-control)

---

## File and Directory Operations

### `ls` - List Directory Contents
**Definition:** Lists files and directories in the current or specified directory.

**Syntax:** `ls [options] [directory]`

**Examples:**
```bash
ls                    # List current directory
ls -l                 # Long format listing
ls -la                # Include hidden files in long format
ls -lh                # Human-readable file sizes
ls -lt                # Sort by modification time
ls -lS                # Sort by file size
ls -R                 # Recursive listing
ls /home/user         # List specific directory
ls *.txt              # List all .txt files
ls -ld */             # List only directories
```

### `cd` - Change Directory
**Definition:** Changes the current working directory.

**Syntax:** `cd [directory]`

**Examples:**
```bash
cd                    # Go to home directory
cd ~                  # Go to home directory
cd /                  # Go to root directory
cd ..                 # Go up one directory
cd ../..              # Go up two directories
cd -                  # Go to previous directory
cd /home/user/docs    # Go to specific directory
cd ~/Documents        # Go to Documents in home
```

### `pwd` - Print Working Directory
**Definition:** Displays the current working directory path.

**Syntax:** `pwd [options]`

**Examples:**
```bash
pwd                   # Show current directory
pwd -L                # Show logical path (default)
pwd -P                # Show physical path (resolve symlinks)
```

### `mkdir` - Make Directory
**Definition:** Creates directories.

**Syntax:** `mkdir [options] directory_name`

**Examples:**
```bash
mkdir mydir           # Create single directory
mkdir dir1 dir2 dir3  # Create multiple directories
mkdir -p path/to/dir  # Create parent directories if needed
mkdir -m 755 mydir    # Create with specific permissions
mkdir -v mydir        # Verbose output
mkdir -p ~/projects/{web,mobile,desktop}  # Create nested structure
```

### `rmdir` - Remove Empty Directory
**Definition:** Removes empty directories.

**Syntax:** `rmdir [options] directory_name`

**Examples:**
```bash
rmdir mydir           # Remove empty directory
rmdir -v mydir        # Verbose removal
rmdir -p path/to/dir  # Remove directory and empty parents
rmdir dir1 dir2       # Remove multiple empty directories
```

### `rm` - Remove Files and Directories
**Definition:** Deletes files and directories.

**Syntax:** `rm [options] file/directory`

**Examples:**
```bash
rm file.txt           # Remove file
rm -i file.txt        # Interactive removal (ask confirmation)
rm -f file.txt        # Force removal (no prompts)
rm -r directory       # Remove directory recursively
rm -rf directory      # Force recursive removal
rm -v file.txt        # Verbose removal
rm *.tmp              # Remove all .tmp files
rm -rf /path/to/dir   # Dangerous: force remove directory tree
```

### `cp` - Copy Files and Directories
**Definition:** Copies files and directories.

**Syntax:** `cp [options] source destination`

**Examples:**
```bash
cp file1.txt file2.txt        # Copy file
cp -i file1.txt file2.txt     # Interactive copy (ask before overwrite)
cp -r dir1 dir2               # Copy directory recursively
cp -p file1.txt file2.txt     # Preserve attributes
cp -u file1.txt file2.txt     # Copy only if source is newer
cp -v file1.txt file2.txt     # Verbose copy
cp file.txt ~/backup/         # Copy to directory
cp *.txt backup/              # Copy all .txt files
cp -a dir1 dir2               # Archive copy (preserve all)
```

### `mv` - Move/Rename Files and Directories
**Definition:** Moves or renames files and directories.

**Syntax:** `mv [options] source destination`

**Examples:**
```bash
mv file1.txt file2.txt        # Rename file
mv file.txt /home/user/       # Move file to directory
mv -i file1.txt file2.txt     # Interactive move
mv -u file1.txt file2.txt     # Move only if source is newer
mv -v file1.txt file2.txt     # Verbose move
mv dir1 dir2                  # Rename directory
mv *.txt documents/           # Move all .txt files
```

---

## File Content Operations

### `cat` - Display File Content
**Definition:** Displays the content of files.

**Syntax:** `cat [options] file`

**Examples:**
```bash
cat file.txt                  # Display file content
cat file1.txt file2.txt       # Display multiple files
cat -n file.txt               # Show line numbers
cat -b file.txt               # Number non-blank lines
cat -s file.txt               # Squeeze blank lines
cat -A file.txt               # Show all characters (including hidden)
cat > newfile.txt             # Create file (Ctrl+D to save)
cat file1.txt > file2.txt     # Copy file content
```

### `less` - View File Content Page by Page
**Definition:** Views file content one page at a time.

**Syntax:** `less [options] file`

**Examples:**
```bash
less file.txt                 # View file
less +F file.txt              # Follow file (like tail -f)
less +G file.txt              # Start at end of file
less -N file.txt              # Show line numbers
less -S file.txt              # Don't wrap long lines
less +/pattern file.txt       # Start at first match of pattern
```

### `more` - View File Content Page by Page
**Definition:** Views file content one page at a time (simpler than less).

**Syntax:** `more [options] file`

**Examples:**
```bash
more file.txt                 # View file
more +10 file.txt             # Start at line 10
more -s file.txt              # Squeeze blank lines
```

### `head` - Display First Lines of File
**Definition:** Shows the first lines of a file.

**Syntax:** `head [options] file`

**Examples:**
```bash
head file.txt                 # Show first 10 lines
head -n 20 file.txt           # Show first 20 lines
head -5 file.txt              # Show first 5 lines
head -c 100 file.txt          # Show first 100 characters
head -v file.txt              # Verbose (show filename)
head file1.txt file2.txt      # Show first lines of multiple files
```

### `tail` - Display Last Lines of File
**Definition:** Shows the last lines of a file.

**Syntax:** `tail [options] file`

**Examples:**
```bash
tail file.txt                 # Show last 10 lines
tail -n 20 file.txt           # Show last 20 lines
tail -5 file.txt              # Show last 5 lines
tail -f file.txt              # Follow file (monitor for changes)
tail -F file.txt              # Follow file name (even if recreated)
tail -c 100 file.txt          # Show last 100 characters
tail -f /var/log/syslog       # Monitor log file
```

### `touch` - Create Empty Files or Update Timestamps
**Definition:** Creates empty files or updates file timestamps.

**Syntax:** `touch [options] file`

**Examples:**
```bash
touch newfile.txt             # Create empty file
touch file1.txt file2.txt     # Create multiple files
touch -a file.txt             # Update access time only
touch -m file.txt             # Update modification time only
touch -c file.txt             # Don't create file if it doesn't exist
touch -t 202301011200 file.txt # Set specific timestamp
touch -r ref.txt file.txt     # Use reference file's timestamp
```

---

## File Permissions and Ownership

### `chmod` - Change File Permissions
**Definition:** Changes file and directory permissions.

**Syntax:** `chmod [options] permissions file`

**Examples:**
```bash
chmod 755 file.txt            # Set rwxr-xr-x permissions
chmod +x script.sh            # Add execute permission
chmod -w file.txt             # Remove write permission
chmod u+x file.txt            # Add execute for user
chmod g-w file.txt            # Remove write for group
chmod o+r file.txt            # Add read for others
chmod a+x file.txt            # Add execute for all
chmod -R 755 directory        # Recursive permission change
chmod u=rwx,go=rx file.txt    # Set specific permissions
```

### `chown` - Change File Ownership
**Definition:** Changes file and directory ownership.

**Syntax:** `chown [options] owner[:group] file`

**Examples:**
```bash
chown user file.txt           # Change owner
chown user:group file.txt     # Change owner and group
chown :group file.txt         # Change group only
chown -R user:group dir       # Recursive ownership change
chown --reference=ref.txt file.txt # Use reference file
chown -v user file.txt        # Verbose output
```

### `chgrp` - Change Group Ownership
**Definition:** Changes group ownership of files and directories.

**Syntax:** `chgrp [options] group file`

**Examples:**
```bash
chgrp group file.txt          # Change group
chgrp -R group directory      # Recursive group change
chgrp -v group file.txt       # Verbose output
chgrp --reference=ref.txt file.txt # Use reference file
```

### `umask` - Set Default Permissions
**Definition:** Sets default permissions for newly created files.

**Syntax:** `umask [permissions]`

**Examples:**
```bash
umask                         # Show current umask
umask 022                     # Set umask to 022
umask -S                      # Show symbolic representation
umask u=rwx,g=rx,o=rx        # Set symbolic umask
```

---

## Process Management

### `ps` - Display Running Processes
**Definition:** Shows information about running processes.

**Syntax:** `ps [options]`

**Examples:**
```bash
ps                            # Show current user's processes
ps aux                        # Show all processes (detailed)
ps -ef                        # Show all processes (full format)
ps -u username                # Show processes for specific user
ps -p 1234                    # Show specific process by PID
ps axjf                       # Show process tree
ps --sort=-%cpu               # Sort by CPU usage
ps --sort=-%mem               # Sort by memory usage
```

### `top` - Display and Monitor Processes
**Definition:** Displays and continuously updates running processes.

**Syntax:** `top [options]`

**Examples:**
```bash
top                           # Start top
top -u username               # Show processes for specific user
top -p 1234,5678              # Monitor specific PIDs
top -d 5                      # Update every 5 seconds
top -n 10                     # Run for 10 iterations then exit
```

### `htop` - Enhanced Process Viewer
**Definition:** Enhanced version of top with better interface.

**Syntax:** `htop [options]`

**Examples:**
```bash
htop                          # Start htop
htop -u username              # Show processes for specific user
htop -p 1234,5678             # Monitor specific PIDs
htop -d 50                    # Update delay (tenths of seconds)
```

### `kill` - Terminate Processes
**Definition:** Sends signals to processes to terminate them.

**Syntax:** `kill [options] PID`

**Examples:**
```bash
kill 1234                     # Send TERM signal to process
kill -9 1234                  # Send KILL signal (force kill)
kill -STOP 1234               # Stop (pause) process
kill -CONT 1234               # Continue stopped process
kill -l                       # List all available signals
kill -HUP 1234                # Send hangup signal
killall firefox               # Kill all firefox processes
```

### `jobs` - Display Active Jobs
**Definition:** Shows active jobs in the current shell.

**Syntax:** `jobs [options]`

**Examples:**
```bash
jobs                          # List active jobs
jobs -l                       # List with PID numbers
jobs -p                       # List PID numbers only
jobs -r                       # List running jobs only
jobs -s                       # List stopped jobs only
```

### `bg` - Put Jobs in Background
**Definition:** Puts jobs in the background.

**Syntax:** `bg [job_id]`

**Examples:**
```bash
bg                            # Put current job in background
bg %1                         # Put job 1 in background
bg %+                         # Put most recent job in background
```

### `fg` - Bring Jobs to Foreground
**Definition:** Brings jobs to the foreground.

**Syntax:** `fg [job_id]`

**Examples:**
```bash
fg                            # Bring current job to foreground
fg %1                         # Bring job 1 to foreground
fg %-                         # Bring previous job to foreground
```

### `nohup` - Run Commands Immune to Hangups
**Definition:** Runs commands that continue after logout.

**Syntax:** `nohup command [arguments]`

**Examples:**
```bash
nohup ./script.sh             # Run script immune to hangup
nohup ./script.sh &           # Run in background
nohup python app.py > output.log 2>&1 & # Redirect output
```

---

## System Information

### `uname` - System Information
**Definition:** Displays system information.

**Syntax:** `uname [options]`

**Examples:**
```bash
uname                         # Show kernel name
uname -a                      # Show all information
uname -s                      # Show kernel name
uname -r                      # Show kernel release
uname -v                      # Show kernel version
uname -m                      # Show machine hardware
uname -p                      # Show processor type
uname -o                      # Show operating system
```

### `whoami` - Current Username
**Definition:** Displays the current username.

**Syntax:** `whoami`

**Examples:**
```bash
whoami                        # Show current username
```

### `who` - Logged in Users
**Definition:** Shows who is logged into the system.

**Syntax:** `who [options]`

**Examples:**
```bash
who                           # Show logged in users
who -a                        # Show all information
who -b                        # Show boot time
who -q                        # Show user count
who -u                        # Show idle time
who am i                      # Show current user info
```

### `w` - Show Logged in Users and Activity
**Definition:** Shows logged in users and their activity.

**Syntax:** `w [options] [user]`

**Examples:**
```bash
w                             # Show all users and activity
w username                    # Show specific user activity
w -h                          # Don't show header
w -s                          # Short format
```

### `id` - User and Group IDs
**Definition:** Shows user and group IDs.

**Syntax:** `id [options] [user]`

**Examples:**
```bash
id                            # Show current user's IDs
id username                   # Show specific user's IDs
id -u                         # Show user ID only
id -g                         # Show group ID only
id -G                         # Show all group IDs
id -n -u                      # Show username
```

### `date` - Display or Set Date
**Definition:** Displays or sets the system date.

**Syntax:** `date [options] [format]`

**Examples:**
```bash
date                          # Show current date and time
date +"%Y-%m-%d"             # Show date in YYYY-MM-DD format
date +"%H:%M:%S"             # Show time in HH:MM:SS format
date +"%A, %B %d, %Y"        # Show full date format
date -d "tomorrow"           # Show tomorrow's date
date -d "2 days ago"         # Show date 2 days ago
date -s "2023-12-25 10:30:00" # Set date and time
```

### `uptime` - System Uptime
**Definition:** Shows how long the system has been running.

**Syntax:** `uptime [options]`

**Examples:**
```bash
uptime                        # Show uptime and load
uptime -p                     # Show uptime in pretty format
uptime -s                     # Show boot time
```

### `df` - Display Filesystem Usage
**Definition:** Shows filesystem disk space usage.

**Syntax:** `df [options] [filesystem]`

**Examples:**
```bash
df                            # Show all filesystems
df -h                         # Human readable format
df -T                         # Show filesystem type
df -i                         # Show inode usage
df /home                      # Show specific filesystem
df -x tmpfs                   # Exclude filesystem type
```

### `du` - Display Directory Usage
**Definition:** Shows directory disk usage.

**Syntax:** `du [options] [directory]`

**Examples:**
```bash
du                            # Show current directory usage
du -h                         # Human readable format
du -s                         # Summary (total only)
du -a                         # Show all files
du -d 1                       # Limit depth to 1 level
du --max-depth=2             # Limit depth to 2 levels
du -sh /home/user            # Show summary of specific directory
```

### `free` - Display Memory Usage
**Definition:** Shows memory usage information.

**Syntax:** `free [options]`

**Examples:**
```bash
free                          # Show memory usage
free -h                       # Human readable format
free -m                       # Show in MB
free -g                       # Show in GB
free -s 5                     # Update every 5 seconds
free -t                       # Show totals
```

---

## Network Commands

### `ping` - Test Network Connectivity
**Definition:** Tests network connectivity to a host.

**Syntax:** `ping [options] host`

**Examples:**
```bash
ping google.com               # Ping google.com
ping -c 4 google.com          # Ping 4 times
ping -i 2 google.com          # Ping every 2 seconds
ping -s 1000 google.com       # Set packet size to 1000 bytes
ping -W 5 google.com          # Set timeout to 5 seconds
ping -f google.com            # Flood ping (root only)
```

### `wget` - Download Files from Web
**Definition:** Downloads files from web servers.

**Syntax:** `wget [options] URL`

**Examples:**
```bash
wget http://example.com/file.zip     # Download file
wget -O newname.zip http://example.com/file.zip # Save with different name
wget -c http://example.com/file.zip  # Continue partial download
wget -r http://example.com/          # Recursive download
wget --limit-rate=100k http://example.com/file.zip # Limit download speed
wget -b http://example.com/file.zip  # Download in background
```

### `curl` - Transfer Data from Servers
**Definition:** Transfers data from or to servers.

**Syntax:** `curl [options] URL`

**Examples:**
```bash
curl http://example.com              # Display webpage content
curl -O http://example.com/file.zip  # Download file
curl -o newname.zip http://example.com/file.zip # Save with different name
curl -I http://example.com           # Show headers only
curl -L http://example.com           # Follow redirects
curl -u user:pass http://example.com # Use authentication
curl -X POST http://example.com/api  # Send POST request
```

### `ssh` - Secure Shell Remote Login
**Definition:** Connects to remote systems securely.

**Syntax:** `ssh [options] user@host`

**Examples:**
```bash
ssh user@server.com               # Connect to remote server
ssh -p 2222 user@server.com       # Connect on specific port
ssh -i ~/.ssh/mykey user@server.com # Use specific key
ssh -X user@server.com            # Enable X11 forwarding
ssh -L 8080:localhost:80 user@server.com # Local port forwarding
ssh -v user@server.com            # Verbose connection
```

### `scp` - Secure Copy over Network
**Definition:** Copies files securely over network.

**Syntax:** `scp [options] source destination`

**Examples:**
```bash
scp file.txt user@server.com:/home/user/ # Copy file to remote
scp user@server.com:/path/file.txt .     # Copy file from remote
scp -r directory user@server.com:/home/  # Copy directory recursively
scp -P 2222 file.txt user@server.com:/   # Use specific port
scp -i ~/.ssh/mykey file.txt user@server.com:/ # Use specific key
```

---

## Archive and Compression

### `tar` - Archive Files
**Definition:** Creates and extracts archive files.

**Syntax:** `tar [options] archive_name files`

**Examples:**
```bash
tar -cvf archive.tar file1 file2     # Create archive
tar -xvf archive.tar                 # Extract archive
tar -tvf archive.tar                 # List archive contents
tar -czvf archive.tar.gz directory   # Create compressed archive
tar -xzvf archive.tar.gz             # Extract compressed archive
tar -cjvf archive.tar.bz2 directory  # Create bzip2 compressed archive
tar -xjvf archive.tar.bz2            # Extract bzip2 compressed archive
tar --exclude='*.log' -czf backup.tar.gz /home/user # Exclude files
```

### `gzip` - Compress Files
**Definition:** Compresses files using gzip compression.

**Syntax:** `gzip [options] file`

**Examples:**
```bash
gzip file.txt                        # Compress file
gzip -d file.txt.gz                  # Decompress file
gzip -c file.txt > file.txt.gz       # Keep original file
gzip -r directory                    # Compress all files in directory
gzip -9 file.txt                     # Maximum compression
gzip -1 file.txt                     # Fastest compression
```

### `gunzip` - Decompress gzip Files
**Definition:** Decompresses gzip compressed files.

**Syntax:** `gunzip [options] file.gz`

**Examples:**
```bash
gunzip file.txt.gz                   # Decompress file
gunzip -c file.txt.gz > file.txt     # Keep compressed file
gunzip -t file.txt.gz                # Test compressed file
```

### `zip` - Create ZIP Archives
**Definition:** Creates ZIP format archives.

**Syntax:** `zip [options] archive.zip files`

**Examples:**
```bash
zip archive.zip file1 file2          # Create zip archive
zip -r archive.zip directory         # Recursively zip directory
zip -e archive.zip file.txt          # Create encrypted zip
zip -9 archive.zip file.txt          # Maximum compression
zip -j archive.zip path/to/file.txt  # Don't store directory structure
```

### `unzip` - Extract ZIP Archives
**Definition:** Extracts ZIP format archives.

**Syntax:** `unzip [options] archive.zip`

**Examples:**
```bash
unzip archive.zip                    # Extract zip archive
unzip -l archive.zip                 # List archive contents
unzip -t archive.zip                 # Test archive integrity
unzip -d /path/to/extract archive.zip # Extract to specific directory
unzip -j archive.zip                 # Extract without directory structure
unzip -o archive.zip                 # Overwrite files without asking
```

---

## Text Processing

### `grep` - Search Text Patterns
**Definition:** Searches for patterns in text files.

**Syntax:** `grep [options] pattern file`

**Examples:**
```bash
grep "pattern" file.txt              # Search for pattern
grep -i "pattern" file.txt           # Case insensitive search
grep -v "pattern" file.txt           # Invert match (exclude lines)
grep -n "pattern" file.txt           # Show line numbers
grep -r "pattern" directory          # Recursive search
grep -l "pattern" *.txt              # Show only filenames
grep -c "pattern" file.txt           # Count matches
grep -A 3 "pattern" file.txt         # Show 3 lines after match
grep -B 3 "pattern" file.txt         # Show 3 lines before match
grep -C 3 "pattern" file.txt         # Show 3 lines before and after
grep "^start" file.txt               # Lines starting with "start"
grep "end$" file.txt                 # Lines ending with "end"
```

### `sed` - Stream Editor
**Definition:** Stream editor for filtering and transforming text.

**Syntax:** `sed [options] 'command' file`

**Examples:**
```bash
sed 's/old/new/' file.txt            # Replace first occurrence per line
sed 's/old/new/g' file.txt           # Replace all occurrences
sed 's/old/new/gi' file.txt          # Case insensitive replacement
sed -n '5p' file.txt                 # Print line 5
sed -n '1,10p' file.txt              # Print lines 1-10
sed '5d' file.txt                    # Delete line 5
sed '/pattern/d' file.txt            # Delete lines containing pattern
sed -i 's/old/new/g' file.txt        # Edit file in place
sed 's/^/> /' file.txt               # Add "> " to beginning of each line
```

### `awk` - Pattern Scanning and Processing
**Definition:** Pattern scanning and data extraction tool.

**Syntax:** `awk 'pattern { action }' file`

**Examples:**
```bash
awk '{print $1}' file.txt            # Print first column
awk '{print $NF}' file.txt           # Print last column
awk '{print NR, $0}' file.txt        # Add line numbers
awk '/pattern/ {print}' file.txt     # Print lines matching pattern
awk '{sum += $1} END {print sum}' file.txt # Sum first column
awk -F: '{print $1}' /etc/passwd     # Use : as field separator
awk 'length > 80' file.txt           # Print lines longer than 80 chars
awk '{print $2, $1}' file.txt        # Swap first two columns
```

### `sort` - Sort Lines
**Definition:** Sorts lines in text files.

**Syntax:** `sort [options] file`

**Examples:**
```bash
sort file.txt                        # Sort alphabetically
sort -n file.txt                     # Sort numerically
sort -r file.txt                     # Reverse sort
sort -u file.txt                     # Sort and remove duplicates
sort -k 2 file.txt                   # Sort by second column
sort -t: -k 3 -n /etc/passwd         # Sort by 3rd field using : separator
sort -f file.txt                     # Case insensitive sort
sort -M file.txt                     # Sort by month names
```

### `uniq` - Remove Duplicate Lines
**Definition:** Removes or reports duplicate lines.

**Syntax:** `uniq [options] file`

**Examples:**
```bash
uniq file.txt                        # Remove consecutive duplicates
uniq -d file.txt                     # Show only duplicate lines
uniq -u file.txt                     # Show only unique lines
uniq -c file.txt                     # Count occurrences
uniq -i file.txt                     # Case insensitive comparison
sort file.txt | uniq                 # Remove all duplicates
```

### `wc` - Word, Line, Character Count
**Definition:** Counts words, lines, and characters in files.

**Syntax:** `wc [options] file`

**Examples:**
```bash
wc file.txt                          # Show lines, words, characters
wc -l file.txt                       # Count lines only
wc -w file.txt                       # Count words only
wc -c file.txt                       # Count characters only
wc -m file.txt                       # Count characters (multibyte aware)
wc *.txt                             # Count for multiple files
```

### `cut` - Extract Columns
**Definition:** Extracts columns from text files.

**Syntax:** `cut [options] file`

**Examples:**
```bash
cut -c 1-10 file.txt                 # Extract characters 1-10
cut -f 1,3 file.txt                  # Extract fields 1 and 3
cut -d: -f 1 /etc/passwd             # Use : as delimiter, extract field 1
cut -d, -f 2- file.csv               # Extract from field 2 to end
cut -c 5- file.txt                   # Extract from character 5 to end
```

### `tr` - Translate Characters
**Definition:** Translates or deletes characters.

**Syntax:** `tr [options] set1 [set2]`

**Examples:**
```bash
tr 'a-z' 'A-Z' < file.txt            # Convert to uppercase
tr -d ' ' < file.txt                 # Delete spaces
tr -s ' ' < file.txt                 # Squeeze multiple spaces to one
tr '\n' ' ' < file.txt               # Replace newlines with spaces
tr -cd '0-9\n' < file.txt            # Keep only digits and newlines
echo "hello" | tr 'l' 'L'            # Replace specific characters
```

---

## Search and Find

### `find` - Find Files and Directories
**Definition:** Searches for files and directories.

**Syntax:** `find [path] [options] [tests] [actions]`

**Examples:**
```bash
find . -name "*.txt"                 # Find .txt files in current directory
find /home -user username            # Find files owned by user
find . -type f -size +100M           # Find files larger than 100MB
find . -type d -name "temp*"         # Find directories starting with "temp"
find . -mtime -7                     # Find files modified in last 7 days
find . -perm 755                     # Find files with specific permissions
find . -name "*.log" -delete         # Find and delete .log files
find . -name "*.txt" -exec grep "pattern" {} \; # Execute command on found files
find . -empty                        # Find empty files and directories
find . -type f -executable           # Find executable files
```

### `locate` - Find Files by Name
**Definition:** Finds files by name using a database.

**Syntax:** `locate [options] pattern`

**Examples:**
```bash
locate filename.txt                  # Find file by name
locate -i filename.txt               # Case insensitive search
locate -c "*.pdf"                    # Count matching files
locate -r "\.txt$"                   # Use regex pattern
updatedb                             # Update locate database (as root)
```

### `which` - Locate Command
**Definition:** Shows the path of commands.

**Syntax:** `which command`

**Examples:**
```bash
which python                         # Show path to python
which -a python                      # Show all paths to python
which ls grep cat                    # Show paths to multiple commands
```

### `whereis` - Locate Binary, Source, Manual
**Definition:** Locates binary, source, and manual page files.

**Syntax:** `whereis [options] command`

**Examples:**
```bash
whereis ls                           # Find ls binary, source, manual
whereis -b ls                        # Find binary only
whereis -m ls                        # Find manual only
whereis -s gcc                       # Find source only
```

---

## System Control

### `sudo` - Execute as Another User
**Definition:** Executes commands as another user (typically root).

**Syntax:** `sudo [options] command`

**Examples:**
```bash
sudo command                         # Run command as root
sudo -u username command             # Run command as specific user
sudo -i                              # Start interactive root shell
: Last argument of previous command

### File Permissions:
- **Read (r)**: 4
- **Write (w)**: 2  
- **Execute (x)**: 1
- **Common combinations**: 755 (rwxr-xr-x), 644 (rw-r--r--), 600 (rw-------)

---

*This guide covers the fundamental Linux commands essential for system administration, development, and daily usage. Practice these commands in a safe environment to become proficient with Linux command-line operations.*
