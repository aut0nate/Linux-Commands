# Linux Commands & Tools Cheatsheet

[![Linux](https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black)](#)

This repository contains a collection of Linux commands and tools that I’ve found particularly useful. I have grouped this into categories for easy reference.

Inspired by: <a href="https://github.com/trinib/Linux-Bash-Commands">trinib/Linux-Bash-Commands</a></p>

---

## Contents

- [Command Information](#command-information)
- [Command History](#command-history)
- [Navigating Directories](#navigating-directories)
- [Managing Directories](#managing-directories)
- [Managing Files](#managing-files)
- [Viewing & Processing Files](#viewing--processing-files)
- [Redirection & Pipelines](#redirection--pipelines)
- [Finding Files & Directories](#finding-files--directories)
- [Archiving & Compressing Files](#archiving--compressing-files)
  - [tar](#tar)
  - [zip & unzip](#zip--unzip)
  - [gzip & gunzip](#gzip--gunzip)
  - [xz](#xz)
- [Searching, Filtering & Modifying Data](#searching-filtering--modifying-data)
  - [grep](#grep)
  - [sed](#sed)
- [User Management](#user-management)
  - [Add User](#add-user)
  - [Modify User](#modify-user)
  - [Remove User](#remove-user)
  - [Add Group](#add-group)
  - [Modify Group](#modify-group)
  - [Remove Group](#remove-group)
- [Text Editors](#text-editors)
  - [nano](#nano)
- [Package Management](#package-management)
  - [Debian / Ubuntu](#debian--ubuntu)
  - [Fedora](#fedora)
- [Process Management](#process-management)
  - [Process Priority](#process-priority)
  - [Killing Processes](#killing-processes)
  - [Jobs](#jobs)
  - [List of Open Files](#list-of-open-files)
- [System Management](#system-management)
  - [CPU](#cpu)
  - [Memory](#memory)
  - [Disk](#disk)
  - [Hardware](#hardware)
- [Network Management](#network-management)
  - [Network Troubleshooting](#network-troubleshooting)
  - [DNS](#dns)
  - [HTTP Requests](#http-requests)
    - [curl](#curl)
    - [wget](#wget)
- [Systemd](#systemd)
  - [systemctl](#systemctl)
  - [journalctl](#journalctl)
- [Scheduled Tasks](#scheduled-tasks)
  - [cron](#cron)
  - [at](#cron)
  - [anacron](#anacron)
- [Terminal Multiplexers](#terminal-multiplexers)
- [Secure Shell Protocol (SSH)](#secure-shell-protocol-ssh)
- [Secure Copy (SCP)](#secure-copy-scp)
- [Rsync](#rsync)
- [Shell Profile](#shell-profile)
- [Environment Variables](#environment-variables)
- [Scripting](#scripting)
  - [Variables](#variables)
  - [Conditional Statements](#conditional-statements)
    - [Boolean Operators](#boolean-operators)
    - [Numeric Operators](#numeric-operators)
    - [String Operators](#string-operators)
    - [IF Statements](#if-statements)
    - [While Loops](#while-loops)
    - [For Loops](#for-loops)
    - [Case Statements](#case-statements)
  - [Functions](#functions)
  
## Command Information

```bash
# Display man page of a command
man <command>                   

# Search man pages for a keyword (similar to apropos)
man -k <query>

# Search the man pages for a keyword
apropos <query>

# Display usage options of a command
<command> --help

# Indentify the type of command such as binary, shell builtin, function or alias
type <command>

# Display all locations of an executable
type -a <command>                              

# Display the executable path for a command (only lists path for executable programs)
which <command>

# Display all executable paths for a command (only lists path for executable programs)
which -a <command>

# Find the binary, source, and manual page files
whereis <command>

# Provide a one line description of what a command does
whatis <command>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Command History

```bash
# View all previous commands
history

# Display the last 10 commands (in `zsh` it displays all commands starting from the 10th)
history 10

# Clears all commands from history
history -c

# Clear a command from a specific line
history -d <line_num>                         

# View the commands using a specific word
history | grep <query>                 

# Run the last command executed
!!                                     

# TIP
# Add a space before the command to prevent the command from showing in history
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Navigating Directories

```bash
# Print current directory path
pwd                       

# List files and directories in the current directory
ls

# List files and directories in long format with detailed information
ls -l

# List files and directories in long format using human-readable units (KiB, MiB, GiB):
ls -lh

# List files and directories in long format including hidden files
ls -la

# List files and directories in long format including hidden files (omits . & ..)
ls -lAh

# List files and directories in long format sorted by modification time (newest to oldest)
ls -lt

# List files and directories in long format sorted by modification time in reverse (oldest to newest)
ls -ltr

# List files and directories in long format sorted by access time (newest to oldest)
ls -ltu

# List files and directories in long format sorted by change time (newest to oldest)
ls -ltc

# List files and directories in long format sorted by size largest to smallest
ls -lhS

# List files in long format sorted by extension type
ls -lX

# List files and directories in long format recursively
ls -lR

# List files and directories in long format displayed with inode numbers
ls -li

# List files and directories in long format sorted numerically by the digits in the file name
ls -lv

# List files in long format, excluding specific files by extension type
ls -lh --hide="*.<extension_type>"

# List files and directories in long format with full timestamps
ls -l --full-time

# List files one per line
ls -1

# List directories in long format
ls -ld */

# List files only
ls -p | grep -v /

# List directory and file tree
tree

# List directory and file tree including hidden files
tree -a

# List directory tree
tree -d

# Change to a directory
cd <directory>

# Change to home directory
cd                        
cd ~              

# Change to the previously chosen directory
cd -                      

# Change to the parent of the current directory:
cd ..

# Pushes the current directory to the top of a stack while changing to the specified directory
pushd <directory>

# Change back to the directory in the stack saved by `pushd`
popd                      
```
[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Managing Directories
  
```bash
# Create a directory
mkdir <directory>

# Create multiple directories
mkdir <directory1> <directory2>

# Create a nested directory
mkdir -p <directory1/directory2>

# Create a temporary directory
mktemp -d

# Delete non-empty directory
rmdir <directory>                     

# Delete directory including contents
rm -r <directory>       
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Managing Files

```bash
# Create a new empty file or update the timestamp of an existing file
touch <file>

# Create multiple files
touch file{1..3}

# Create a new empty file with a specific date
touch -d "yyyy-mm-dd hh:mm:ss" <file>

# Change the access time of a file to the current time
touch -a <file>
 
# Change the modification time of a file to the current time
touch -m <file>
 
# Change the modification time of a file to a specific date and time
touch -m -t 201812301530.45 <file>
 
# Change the timestamp of a file to that of another file
touch -r <file1> <file2>

# Copy a file to another file or directory
cp <file> <file/directory>

# Copy a file to a destination, only if the source file is newer than the destination file
cp -u <file> <destination>

# Copy a file and prompt before overwriting
cp -i <file> <destination>

# Copy a file, but does not overwrite existing files at the destination
cp -n <file> <destination>

# Copy a file while preserving file attributes such as timestamps and permissions
cp -p <file> <destination>

# Recursively copies the directory and all its contents to the destination directory
cp -r <directory> <destination>

# Copies a file with verbose output
cp -v <file> <destination>

# Move a file to a directory
mv <file> <directory>

# Move or rename a file to a destination, only if the source file is newer than the destination file
mv -u <file> <destination>

# Move or rename a file and prompt before overwriting
mv -i <file1> <destination>

# Moves files or directories, but does not overwrite existing files at the destination
mv -n <source> <destination>

# Makes a backup of the destination file before overwriting with the source file
mv -b <file> <destination>

# Move or rename a file with verbose output
mv -v <file1> <destination>

# Rename a file
mv <file> <new_filename>

# Remove a file or directory
rm <file>

# Remove a directory and its contents recursively (use with extreme caution)
rm -rf <directory>

# Recursively delete a directory and its contents, with interactive prompts to confirm each deletion
rm -ri

# Recursively delete a directory and its contents, with verbose output to show each deletion
rm -rfv

# Create a hard symbolic link
ln <file1> <file2>

# Create a soft symbolic link
ln -s <file/directory_source> <file/directory_source_link>

# The `tee` command reads from standard input and writes to both standard output and one or more files
# It is useful for logging or saving output while still displaying it in the terminal
ls -lh /usr/bin/g* | tee bin_out.txt | grep -i "glow" 

# Create a temporary file
mktemp 

# Display detailed information about a file or directory
stat <file/directory>

# Display the file type
file <file/directory>

# Display file type for all files within a directory
file /directory/*

# Create a file of a specific size, e.g. B,KB,MB,GB
fallocate -l <size> <file>

# Securely deletes a file by overwriting its contents ~n times, displaying progress and verbose output
shred -vu -n <num> <file>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Viewing & Processing Files

```bash
# Output text to a file via stdout
echo <text> > <file>

# Display the contents of a file
cat <file>

# Display the contents of a file with line numbers
cat -n <file>

# Display the first 10 lines of a file (replace with desired number)
head -n 10 <file>

# Display the last 10 lines of a file (replace with desired number)
tail -n 10 <file>

# Display the contents of a file starting from line ~n (i.e., skips the first ~n lines)
tail -n +<num> <file>

# Display updates to the file in real time
tail -f <file>

# View the contents of a file one screen at a time (use / to search, "g" to navigate to the top, "G" to navigate to the bottom of the file)
less <file>

# View the contents of a file one screen at a time with line numbers
less -N <file>

# Display the number of lines, words, and bytes in a file
wc <file>

# Display the number of lines in a file
wc -l <file>

# Display the number of words in a file
wc -w <file>

# Display the contents of a file with line numbers
nl <file>

# Sort the contents of a file
sort <file>

# Sort the contents of a file numerically
sort -n <file>

# Sort the contents of a file in reverse order
sort -r <file>

# Sort the contents of a file by month in chronological order (e.g., Jan, Feb, Mar, etc.), assuming the month name is present in the file
sort -M <file>

# Sort the contents of a file in human-readable numeric order (e.g., 1K, 2M, 3G) by interpreting size suffixes
sort -h <file>

# Sort the contents of a file and remove duplicate lines
sort -u <file>

# Sort the contents of a file based on the second column (key 2) using the default delimiter (whitespace)
sort -k 2 <file>

# Sort the contents of a file based on the fourth column (key 4) with a comma (,) as the delimiter, and sorts numerically (-n)
sort -t , -k 4 -n <file> 

# Sort the contents of a file based on the fourth column (key 4) with a comma (,) as the delimiter, and sorts numerically in reverse (-nr)
sort -t , -k 4 -nr <file>

# Randomly shuffles the lines in a file, displaying them in a random order
sort -R <file>

# Output the header line, then sort the rest of the file by lines
# - 'head -n 1' gets the first line (header) of <file>
# - 'tail -n +2' skips the header and outputs from the second line onward
# - 'sort' sorts the data rows alphabetically (default)
(head -n 1 <file> && tail -n +2 <file> | sort)

# Output the header, then sort the data by date (month and day)
# - 'head -n 1' gets the first line (header) of <file>
# - 'tail -n +2' skips the header and outputs from the second line onward
# - 'sort -t',' -k4,4n -k3,3M' sorts using:
#     - '-t',' sets comma as the field delimiter
#     - '-k4,4n' sorts numerically by the 4th field (day)
#     - '-k3,3M' sorts by the 3rd field as a month name (e.g., Jan, Feb)
(head -n 1 <events.csv> && tail -n +2 <events.csv> | sort -t',' -k4,4n -k3,3M)

# Filter out repeated lines in a file (adjacent duplicates)
uniq <file>

# Show duplicate lines in a file (adjacent duplicates)
uniq -d <file>

# Show unique lines in a file (adjacent duplicates)
uniq -u <file>

# Counts the lines in a file
uniq -c <file>

# Compare the contents of two files
diff <file1> <file2>

# Compare the contents of two files side-by-side
diff -y <file1> <file2>

# Compare the contents of two files with unified context
diff -u <file1> <file2>

# Cut the second field from a comma-separated file
cut -d , -f 2 <file>

# Merges all lines from a file into a single line separated by spaces
paste -s -d ' ' <file>

# Repeatedly executes <command> every <secs> seconds, highlighting changes in the output
watch -n <secs> -d <command>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Redirection & Pipelines

```bash
# Overwrite the file `<file_name>` with the string "<content>" (creates the file if it doesn't exist)
echo "<content>" > <file_name>

# Append the string "<content>" to the end of the file `<file_name>` (creates the file if it doesn't exist)
echo "<content>" >> <file_name>

# Redirect standard output (stdout) of the `ls` command to the file `<output_file>`
ls -l <directory> 1> <output_file>

# Redirect standard error (stderr) of the `ls` command to the file `<error_file>`
ls -l <directory> 2> <error_file>

# Redirect both standard output and standard error to the file `<output_file>`
ls -l <directory &> <output_file>

# Discard both standard output and standard error by redirecting to `/dev/null`
ls -l <directory> &> /dev/null
```

A pipeline `(|)` connects the output of one command to the input of another, enabling efficient data processing in a chain of commands.

```bash
# Example 1: Pipe the output of `ls` to `grep` to filter results containing "<pattern>"
ls | grep "<pattern>"

# Example 2: Pipe the output of `ps` to `grep` to find a specific process
ps aux | grep "<process_name>"

# Example 3: Count the number of lines in a file using `wc -l`
cat <file_name> | wc -l

# Example 4: Use `cut` to extract specific columns from a file, and then sort the output
cat <file.csv> | cut -d ',' -f 1 | sort

# Example 5: Chain multiple commands to extract and manipulate data
cat <log_file> | grep "<keyword>" | awk '{print $1, $2, $3}' | sort | uniq
```

## Finding Files & Directories

`find` doesn't use an index and searches the file system in real time

```bash
# Find all files and directories in the current directory
find .

# Find a file by name in the current directory
find . -name <file>

# Find all CSV files in the current directory
find . -type f -name '*.csv'

# Find files by case-insensitive name pattern in the current directory
find . -type f -iname "*<file>*"

# Find a file by name in a given directory
find <directory> -name <file>

# Find files with a specific extension in a given directory
find <directory> -name "*.<extension_type>"

# Find all files in a given directory
find <directory> -type f

# Find all directories in a given directory
find <directory> -type d

# Find all symbolic links in a given directory
find <directory> -type l

# Find files by case-insensitive name pattern in a given directory
find <directory> -type f -iname "*<file>*"

# Find all directories containing "proj" in a given directory
find <directory> -type d -name "*proj*"

# mmin = modified minutes
# mtime = modified time (days)
# cmin = changed minutes
# ctime = changed time (days)
# amin = accessed minutes
# atime = accessed time (days)

# Find files modified within the last 24 hours (1 day) in the current directory
find . -type f -mtime 0

# Find files modified within the last 10 minutes in the current directory
find . -type f -mmin -10

# Find files modified more than 10 minutes ago in the current directory
find . -type f -mmin +10

# Find files modified between 1 and 5 minutes ago in the current directory
find . -type f -mmin +1 -mmin -5

# Find files modified within the last 20 days in a given directory
find <directory> -type f -mtime -20

# Find files modified more than 20 days ago in a given directory
find <directory> -type f -mtime +20

# Find files modified within the last 48 hours in a given directory
find <directory> -type f -newermt '48 hours ago'

# Find files modified within the last 30 days in a given directory
find <directory> -type f -newermt '30 days ago'

# Find files modified within the last 5 minutes in a given directory
find <directory> -type f -newermt '5 minutes ago'

# Find all files in /var/ that were modified within the last 24 hours (-mtime 0) and copy the files to /home/user/directory
sudo find /var/ -type f -mtime 0 -exec cp {} /home/user/directory \;

# Find files larger than 300 bytes in the current directory
find . -type f -size +300c

# Find files exactly 4KB in size in a given directory
find <directory> -type f -size 4k

# Find files larger than 5MB in the current directory
find . -type f -size +5M

# Find files less than 1GB in the current directory
find . type f -size -1G

# Find files between 75MB and 100MB in a given directory
find <directory> -type f -size -100M -size +75M

# Find files with read, write, and execute permissions in the current directory
find . -type f -perm 777

# Find files and directories where 'other' has exactly read / write permissions in the current directory
# -perm '-' means match exact permissions
find . -perm -o=rx

# Find files and directories where 'other' has at least read / write permissions in a given directory
# -perm '/' means at least the specified permissions
find <directory> -perm /o=rx

# Find files and directories where 'other' does not have read,write and execute permissions in the current directory
# -perm '/' means at least the specified permissions
find . -not -perm /o=rwx

# Find and delete all files matching the criteria in a given directory without recursing into subdirectories
find <directory> -maxdepth 1 -type f -name "*.<extension_type>" -exec rm -f {} \;
```

`plocate` is a faster, more efficient implementation of locate, which is used to find files on a Linux system by querying a prebuilt index.

```bash
# Since plocate is not installed by default on most systems, you can install it as follows:

# On Debian/Ubuntu-based systems
sudo apt install plocate

# On Fedora-based systems
sudo dnf install plocate

# Search for a file by its name
plocate <filename>

# Search for all files with a .txt extension using a wildcard
plocate "*.txt"

# Limit the number of search results to 10 when searching for a specific file
plocate -n 10 <filename>

# Use regular expression to search for files matching the criteria in the /home/user directory
plocate -r '^/home/user/.*filename'

# Update the plocate database to ensure new or deleted files are reflected in future searches
sudo updatedb
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Searching, Filtering & Modifying Data

### grep

```bash
# Count the total number of lines containing the specified pattern in the file
grep -c <pattern> <file>

# Display matching lines with their corresponding line numbers
grep -n <pattern> <file>

# Perform a case-insensitive search for the specified pattern
grep -i <pattern> <file>

# Display only lines that do not match the specified pattern
grep -v <pattern> <file>

# Display only lines that exactly match the entire pattern (no partial matches)
grep -x <pattern> <file>

# List only the names of files that contain the specified pattern
grep -l <pattern> <directory>

# List only the names of files that do not contain the specified pattern
grep -L <pattern> <directory>

# Search for a pattern using the -e option
grep -e <pattern> <directory>

# Specify multiple patterns using the -E option
grep -E <pattern1|pattern2> <file>

# Use multiple patterns from a file, where each pattern is on a new line
grep -f <pattern_file> <file>

# Recursively search for the pattern in the specified directory and its subdirectories
grep -r <pattern> <directory>

# Search for occurrences of <pattern> in <file> and display matching lines with line numbers (-n) and only the matching part of the line (-o)
grep -on <pattern> <file>

# Search for the whole word (case-insensitive) in the file
grep -wi <pattern> <file>

# Search for the whole word (case-insensitive) and display matching lines with line numbers in the current directory
grep -win <pattern> <file>

# Search for the whole word (case-insensitive) with one line of context before the matching line
grep -win -B 1 <pattern> <file>

# Search for the whole word (case-insensitive) with two lines of context after the matching line
grep -win -A 2 <pattern> <file>

# Search for the whole word (case-insensitive) with two lines of context before and after the matching line
grep -win -C 2 <pattern> <file>

# Recursively search for the whole word (case-insensitive) in all files within the current directory, and display only the match count for each file
grep -wicr <pattern>

# Recursively search for the whole word (case-insensitive) and display only the names of files containing the pattern
grep -wirl <pattern>

# Recursively search for the whole word (case-insensitive) and display matching lines with line numbers in all files within the current directory
grep -winr <pattern>

# Recursively search for the whole word (case-insensitive) in the current directory and all its subdirectories, displaying matching lines with line numbers
grep -win <pattern> ./*

# Search for empty lines in a file and display the line number
grep -n "^$" <file>

# Extract all email addresses from a file using a basic regular expression pattern
grep -E '[a-z]*\.[a-z]*@[a-z]*\.[a-z]*' <file>

# Extract all IPv4 addresses from a file by matching patterns of four dot-separated octets
grep -oE '\b[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\b' <file>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### sed

```bash
# Replace all occurrences of "pattern1" with "pattern2" in <input_file> and display the result in the console
sed 's/pattern1/pattern2/g' <input_file>

# Replace all occurrences of "pattern1" with "pattern2" (case-insensitive) in <input_file> and display the result in the console
sed 's/pattern1/pattern2/gi' <input_file>

# Replace all occurrences of "multi word pattern1" with "multi word pattern2" in <input_file> and display the result in the console
sed 's/multi word pattern1/multi word pattern2/g' <input_file>

# Replace all occurrences of "pattern1" with "pattern2" in <input_file> and save the result to <output_file>
sed 's/pattern1/pattern2/g' <input_file> > <output_file>

# Replace all occurrences of "pattern1" with "pattern2" in <input_file> and overwrite the original file
sed -i 's/pattern1/pattern2/g' <input_file>

# Insert "new text" before lines containing "pattern" in <input_file> and overwrite the original file
sed -i '/pattern/i\new text' <input_file>

# Insert "new text" after lines containing "pattern" in <input_file> and overwrite the original file
sed -i '/pattern/a\new text' <input_file>

# Replace "find_text" with "replace_text" only on the 10th line of <input_file> and overwrite the original file
sed -i '10s/find_text/replace_text/' <input_file>

# Replace "find_text" with "replace_text" on lines 10 through 20 of <input_file> and overwrite the original file
sed -i '10,20s/find_text/replace_text/' <input_file>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Archiving & Compressing Files

### tar

```bash
# Create a tar archive (without compression)
tar -cvf <archive>.tar /path/to/directory

# List the contents of a tar archive
tar -tvf <archive>.tar

# Extract the contents of a tar archive
tar -xvf <archive>.tar

# Create a compressed tar archive using gzip (.tar.gz or .tgz)
tar -czvf <archive>.tar.gz /path/to/directory

# Extract a compressed tar archive (.tar.gz or .tgz)
tar -xzvf <archive>.tar.gz

# Create a compressed tar archive using bzip2 (.tar.bz2 or .tbz)
tar -cjvf <archive>.tar.bz2 /path/to/directory

# Extract a compressed tar archive using bzip2 (.tar.bz2 or .tbz)
tar -xjvf <archive>.tar.bz2

# Create a compressed tar archive using xz (.tar.xz)
tar -cJvf <archive>.tar.xz /path/to/directory

# Extract a compressed tar archive using xz (.tar.xz)
tar -xJvf <archive>.tar.xz

# Extracts the compressed archive file to the specified destination directory
tar -xvf <archive> -C /path/to/directory>

# Automatically compress using gzip, bzip2, or xz based on the file extension

# Compress using gzip (based on .tar.gz extension)
tar -caf <archive>.tar.gz /path/to/directory

# Compress using bzip2 (based on .tar.bz2 extension)
tar -caf <archive>.tar.bz2 /path/to/directory

# Compress using xz (based on .tar.xz extension)
tar -caf <archive>.tar.xz /path/to/directory
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### zip & unzip

```bash
# Compress a single file into a zip archive
zip <archive>.zip <file_name>

# Compress multiple files into a zip archive
zip <archive>.zip <file1> <file2>

# Compress multiple files using brace expansion
zip <archive>.zip {file1,file2}.txt

# Recursively compress a directory and its contents
zip -r <archive>.zip /path/to/directory

# Extract the contents of a zip archive into the current directory
unzip <archive>.zip
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### gzip & gunzip

```bash
# Compress a file using gzip (replaces the original file with the compressed version)
gzip <file>

# Compress a file using gzip and keep the original file
gzip -k <file>

# Compress multiple files using gzip (each file is compressed individually)
gzip <file1> <file2>

# Decompress a .gz file (replaces the compressed file with the original)
gunzip <archive>.gz

# Decompress a .gz file and keep the compressed file
gunzip -k <archive>.gz

# View the contents of a compressed .gz file without decompressing it
zcat <archive>.gz
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### bzip2 & bunzip2

```bash
# Compress a file using bzip2 (replaces the original file with the compressed version)
bzip2 <file>

# Compress a file using bzip2 and keep the original file
bzip2 -k <file>

# Decompress a .bz2 file (replaces the compressed file with the original)
bunzip2 <archive>.bz2

# Decompress a .bz2 file and keep the compressed file
bunzip2 -k <archive>.bz2

# View the contents of a compressed .bz2 file without decompressing it
bzcat <archive>.bz2
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### xz

```bash
# Compress a file using xz (replaces the original file with the compressed version)
xz <file>

# Compress a file using xz and keep the original file
xz -k <file>

# View the contents of a compressed .xz file without decompressing it
xzcat <archive>.xz
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## File Permissions

| # | Permission              | rwx | Binary |
| - | -                       | -   | -      |
| 7 | read, write and execute | rwx | 111    |
| 6 | read and write          | rw- | 110    |
| 5 | read and execute        | r-x | 101    |
| 4 | read only               | r-- | 100    |
| 3 | write and execute       | -wx | 011    |
| 2 | write only              | -w- | 010    |
| 1 | execute only            | --x | 001    |
| 0 | none                    | --- | 000    |

For a directory, execute means you can enter a directory.

| User | Group | Others | Description                                                                                          |
| -    | -     | -      | -                                                                                                    |
| 6    | 4     | 4      | User can read and write, everyone else can read (Default file permissions)                           |
| 7    | 5     | 5      | User can read, write and execute, everyone else can read and execute (Default directory permissions) |

- u - User
- g - Group
- o - Others
- a - All of the above

```bash
# Set permissions to read, write, and execute for the user; read and execute for group and others
chmod 755 <file_or_directory>

# Set permissions to read and write for the user, read only for group and others
chmod 644 <file_or_directory>

# Set strict permissions for files (user can read and write, no access for others)
chmod 600 <file>

# Allow everyone to read and execute a public file, but only the user can write
chmod 755 <file>

# Make a directory accessible to everyone (read, write, and execute)
chmod 777 <directory>

# Set read, write, and execute for the user, and read-only for group and others
chmod u=rwx,g=r,o=r <file>

# Add execute permission for the user
chmod u+x <file>

# Remove write permission for the group
chmod g-w <file>

# Add read permission for others
chmod o+r <file>

# Remove all permissions for others
chmod o= <file>

# Add execute permission for all (user, group, and others)
chmod a+x <file>

# Remove write permission for everyone
chmod a-w <file>

# Set read, write, and execute permissions for the user, and read and execute for group and others, recursively for all files and subdirectories
chmod -R 755 <directory>

# Remove write permissions for others recursively
chmod -R o-w <directory>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## User Management

```bash
# Switch to the root user (superuser mode)
sudo su

# List the commands that the invoking user is allowed or forbidden to run with sudo
sudo -l

# Start an interactive root shell session (grants root access temporarily)
sudo -s

# Invalidate the cached sudo credentials, requiring re-authentication for the next sudo command
sudo -k

# Execute a command with root privileges (useful when permission is denied for a regular user)
sudo <command>

# Safely edit the sudoers file to manage user privileges (always use visudo to avoid syntax errors)
sudo visudo

# Switch to a different user account (prompts for the user's password unless already root)
su <username>

# Switch to a different user account and load their environment (prompts for the user's password unless already root)
su -l <username>

# Execute a specific command as a different user (or root if no user is specified)
su -c "<command>" <username>

# Display the current logged-in username
whoami

# Show who is currently logged in and their activities (includes user, terminal, and process details)
w

# Display all currently logged-in users and their terminal sessions
who

# Display detailed information about the current user (finger package required)
finger $(whoami)

# Display a list of recent logins for all users, including login time, terminal, and IP address
last

# Display recent login information for a specific user
last <username>

# Display the failed login history of users (reads from /var/log/btmp)
lastb

# Display the most recent login information for all users
lastlog

# Display the user ID (UID), group ID (GID), and supplementary group IDs of the current user
id

# Display the groups the current user belongs to
groups

# Display the groups a specified user belongs to
groups <username>

# Display the contents of the /etc/passwd file (contains user account information)
cat /etc/passwd

# Display the contents of the /etc/group file (contains group information)
cat /etc/group

# Display the contents of the /etc/shadow file (contains encrypted password information for user accounts)
sudo cat /etc/shadow

# Change the login shell of a specified user to /usr/sbin/nologin, effectively disabling login for the user
sudo usermod -s /usr/sbin/nologin <username>

# Change the password for the current user or another user (requires root privileges for other users)
sudo passwd <username>

# List the status of all user accounts, showing password information (e.g., locked/unlocked, last password change)
sudo passwd -S -a

# List the usernames of all locked user accounts by filtering the output of the previous command
sudo passwd -S -a | awk '/LK/ {print $1}'

# Display password aging information (e.g., last password change, expiration) for a specified user
chage -l <user>

# Force a specified user to change their password at the next login by setting the last password change date to today
sudo chage --lastday 0 <user>

# Set the maximum number of days before a specified user must change their password (in this case, 2 days)
sudo chage --maxdays 2 <user>

# Remove the maximum password age limit for a specified user, allowing the password to remain unchanged indefinitely
sudo chage --maxdays -1 <user>

# Set the account expiration date for a specified user (YYYY-MM-DD format), after which the account is disabled
sudo chage --expiredate YYYY-MM-DD <user>

# Prompts the user to change the default shell
chsh
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Add User

```bash
# Add a user with default settings (no home directory, no password set)
# To view or modify default settings, use: useradd -D (--defaults)
useradd <username>

# Add a user with a home directory created and the default shell set to /bin/bash
useradd -m -s /bin/bash <username>

# Add a user and specify a custom home directory
useradd -d /home/customhome <username>

# Add a user and specify a custom user ID (UID)
useradd -u 1001 <username>

# Add a user and set their primary group
useradd -g <primary_group> <username>

# Add a user and assign them to multiple supplementary groups
useradd -G group1,group2 <username>

# Add a user and specify a custom login shell
useradd -s /bin/bash <username>

# Add a user and set an account expiration date (after this date, the account is disabled)
useradd -e 2024-12-31 <username>

# Add a user with a custom comment (commonly used to store the full name or additional information)
useradd -c "<Full Name or Comment>" <username>

# Add a user without creating a home directory
useradd -M <username>

# Add a user and set a predefined encrypted password (using OpenSSL for password encryption)
useradd -p $(openssl passwd -crypt 'password') <username>

# Add a user with multiple custom options combined (home directory, UID, primary group, supplementary groups, shell, expiration date, and comment)
useradd -m -d /home/customhome -u 1001 -g users -G group1,group2 -s /bin/bash -e 2024-12-31 -c "<Full Name>" <username>

# Add a system/service account using the -r flag (no password, custom shell, and home directory)
# Service accounts are typically used for daemons and background services
sudo useradd -r -s /bin/false -d /nonexistent -m <service_name>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Modify User

```bash
# Change the user's login name (useful for renaming a user account)
usermod -l <new_username> <old_username>

# Change the user's home directory and move its contents to the new location
usermod -d /home/newhome -m <username>

# Change the user's UID (useful for synchronising UIDs across systems)
usermod -u <new_uid> <username>

# Change the user's primary group (the group assigned by default to newly created files)
usermod -g <group> <username>

# Assign the user to new supplementary groups (this replaces existing supplementary groups)
usermod -G <group1>,<group2> <username>

# Remove the user from all supplementary groups (only the primary group remains)
usermod -G ""

# Add the user to additional groups without removing them from current supplementary groups
usermod -aG <group3>,<group4> <username>

# Change the user's default login shell
usermod -s /bin/zsh <username>

# Set an expiration date for the user's account (after this date, the account will be disabled)
usermod -e <expiration_date> <username>  # Example: usermod -e 2024-12-31 <username>

# Lock the user's account (disables login by placing a "!" in front of the encrypted password)
usermod -L <username>

# Unlock the user's account (removes the "!" from the encrypted password)
usermod -U <username>

# Change or update the user's comment (commonly used to store the user's full name or description)
usermod -c "<Full Name or Comment>" <username>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Remove User

```bash
# Delete a user but keep their home directory and mail spool intact
userdel <username>

# Delete a user and remove their home directory and mail spool
userdel -r <username>

# Forcefully delete a user even if they are currently logged in
userdel -f <username>

# Forcefully delete a user and remove their home directory and mail spool
userdel -r -f <username>

# Delete a user but preserve their home directory and mail spool (only the user account is deleted)
userdel <username>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Add Group

```bash
# Create a new group with default settings
groupadd <new_group>

# Create a new group with a specific Group ID (GID)
groupadd -g <gid> <new_group>

# Create a system group (system groups typically have GIDs below 1000)
groupadd -r <new_group>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Modify Group

```bash
# Change the name of an existing group
groupmod -n <new_group_name> <current_group_name>

# Change the Group ID (GID) of an existing group
groupmod -g <new_gid> <group>

# Add <username> to the specified <group>
sudo gpasswd -a <username> <group>

# Remove <username> from the specified <group>
sudo gpasswd -d <username> <group>

# Set <username> as the group administrator (administrators can add or remove users from the group)
sudo gpasswd -A <username> <group>

# Change the current group ID to <group> for the current session (useful for accessing group-restricted files)
newgrp <group>

# Change the group ownership of a file to the specified <group>
chgrp <group> <file>

# Recursively change the group ownership of a directory and all its contents to the specified <group>
chgrp -R <group> <directory>

# Retrieve information about the specified <group> from the system's group database
getent group <group>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Remove Group

```bash
# Delete a group with default settings
groupdel <group>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Text Editors

### Nano

 ```bash
# Open the nano text editor with a new, unsaved buffer
nano

# Open an existing file in nano for editing
nano <file>

# Enable mouse support in nano (allows using the mouse for cursor positioning and text selection)
nano -m <file>

# Display line numbers on the left-hand side while editing in nano
nano -l <file>

# Open the file in nano and position the cursor at the specified line and column (line 5, column 10 in this example)
nano +5,10 <file>

# Create a backup of the file (`<file_name>~`) when saving changes
nano -B <file>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Package Management

### Debian / Ubuntu

```bash
# Refresh the repository index (update package lists)
apt update

# Upgrade all installed packages to their latest versions
apt upgrade

# Search for a package by name or description
apt search <package>

# Display detailed information about a specific package
apt show <package>

# List installed and available versions of a package
apt list <package>

# List all available versions of a package
apt list --all-versions <package>

# Install the latest version of a package
apt install <package>

# Install a specific version of a package
apt install <package>=<version>

# Remove a package (but keep configuration files)
apt remove <package>

# Automatically remove unused dependencies
apt autoremove

# Clear the local cache of downloaded package files
apt clean

# Install a .deb package file
dpkg -i <package_name>.deb  # or --install <package_name>.deb

# Completely remove a .deb package, including configuration files
dpkg -P <package>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Fedora

```bash
# Refresh the repository index (update package lists)
sudo dnf check-update

# Upgrade all installed packages to their latest versions
sudo dnf upgrade

# Search for a package by name or description
sudo dnf search <package>

# Display detailed information about a specific package
sudo dnf info <package>

# Install the latest version of a package
sudo dnf install <package>

# Install a specific version of a package (if multiple versions are available)
sudo dnf install <package>-<version>

# Remove a package (but keep configuration files)
sudo dnf remove <package>

# Automatically remove unused dependencies
sudo dnf autoremove

# Clean up cached package files and metadata
sudo dnf clean all
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Process Management

```bash
# Display a list of all running processes interactively (with real-time updates)
top

# Display a list of all running processes interactively with a more user-friendly interface (requires htop package)
htop

# Return the PID of all running processes matching a specific name
pidof <command>

# Display all running processes for the current user in a simple format
ps

# Display detailed information about running processes for all users in a detailed format
ps -au

# Display detailed information about all running processes including processes not attached to a terminal, such as system daemons
ps -aux

# Display processes sorted by CPU usage in descending order
ps -aux --sort=-%cpu

# Display processes sorted by memory usage in descending order
ps -aux --sort=-%mem

# Display all running processes for the current user in a detailed format
ps -f

# Display detailed information about all running processes
ps -ef

# Display processes for a specific user
ps -u <username>

# Display detailed information about running processes owned by a specific user
ps -U <username> -u

# Display processes for a specific user with full command line information
ps -u <username> -f

# Display processes matching a specific command name
ps -C <process_name>

# Display threads within all processes
ps -eLf

# Display all processes with a custom output format (showing PID, user, and command)
ps -eo pid,user,cmd

# Display processes for a specific user with custom output, sorted by CPU usage
ps -u <username> -o pid,user,ni,%cpu,%mem,vsz,start,time,stat,cmd --sort=-%cpu

# Display processes for a specific user with custom output, sorted by memory usage
ps -u <username> -o pid,user,ni,%cpu,%mem,vsz,start,time,stat,cmd --sort=-%mem

# Display the nice value of all processes
ps -eo pid,user,ni,cmd

# Display the nice value of all processes for a specific user
ps -u <username> -o pid,user,ni,cmd
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Process Priority

Process priorities go from -20 (highest) to 19 (lowest).

```bash
# Change the nice value of an existing process (requires root privileges for negative values)
sudo renice -5 -p <PID>

# Change the nice value of all processes owned by a specific user
sudo renice -10 -u <username>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Killing Processes

```bash
# Kill a process running in the foreground
CTRL+C                 
# Send the default SIGTERM signal to terminate a process gracefully
kill <PID>

# Forcefully terminate a process using SIGKILL (signal 9)
kill -9 <PID>

# Send a specific signal (e.g., SIGHUP) to a process
kill -1 <PID>

# Terminates all processes by name
killall <name>

# Forcefully terminates all processes by name using SIGKILL (signal 9)
killall -9 <name>

# Send a signal to all processes with a specific command name
pkill -HUP <command_name>

# Send a signal to all processes owned by a specific user
pkill -u <username>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Jobs

```bash
# Resume a suspended process and run it in the background
bg

# Bring the last background process to the foreground
fg

# Bring a specific background job to the foreground (by job number)
fg %<job_number>

# Suspend a process running in the foreground (sends SIGTSTP)
CTRL+Z

# List all background jobs
jobs

# List all background jobs with their PIDs
jobs -l
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### List of Open Files

```bash
# List all open files and the processes using them
lsof

# List all open files in a specific directory
lsof +D /path/to/directory

# List all open files opened by a specific command
lsof -c <command>

# List all open files associated with a specific file descriptor (e.g., 2 for stderr)
lsof -d 2

# List all network connections (both listening and established)
lsof -i

# List all open files and network connections for a specific protocol (TCP/UDP)
lsof -i TCP
lsof -i UDP

# List open files associated with specific port numbers
lsof -i :80     # Port 80 (HTTP)
lsof -i :22     # Port 22 (SSH)

# List open files and network connections for IPv4 or IPv6
lsof -i 4       # IPv4
lsof -i 6       # IPv6

# List open files that have been deleted
lsof +L1

# List all open files along with the associated user
lsof -a -u <username>

# List open files showing file access mode (r = read, w = write, u = read & write)
lsof -a -u <username> -o

# List open files and their corresponding process IDs (PIDs) in numeric form
lsof -n

# List files opened by a specific process and exclude files in a specific directory
lsof -p <PID> | grep -v /path/to/exclude

# Display open files without resolving IP addresses to hostnames
lsof -n -i

# Display the complete command line for each process
lsof -F c

# Find which process is using a specific file
lsof /path/to/file

# Identify the process using a specific network port
lsof -i :8080

# Display all open files for a specific device (e.g., mounted disk)
lsof /dev/sda1

# Identify processes using swap space
lsof | grep swap
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## System Management

```bash
# Show how long the system has been running, including load averages
uptime

# Display the kernel name
uname -s

# Display the kernel release version
uname -r

# Display the system architecture
uname -m

# Display the operating system
uname -o

# Display all system information (kernel name, release, version, architecture, etc.)
uname -a

# Display distribution-specific information (requires lsb-release package)
lsb_release -a

# Display the system architecture (e.g., amd64, i386)
dpkg --print-architecture

# Display operating system identification data (name, version, ID)
cat /etc/os-release

# Display detailed system information, including hostname, kernel, and architecture
hostnamectl

# Change the system hostname
hostnamectl set-hostname <new_hostname>

# Display the init system being used (e.g., systemd or upstart)
ls -l /sbin/init

# Display the current runlevel of the system
runlevel

# Display the default systemd target (e.g., graphical.target, multi-user.target)
systemctl get-default

# Display system logs
journalctl

# Follow system logs in real-time (similar to tail -f)
journalctl -f

# Display the status of a specific system service
systemctl status <service>

# Restart a specific system service
systemctl restart <service>

# Shutdown the system in 1 minute
shutdown

# Immediately shut down the system
shutdown now

# Schedule a shutdown in 5 minutes
shutdown +5

# Reboot the system in 1 minute
shutdown -r

# Immediately reboot the system
shutdown -r now

# Schedule a reboot in 5 minutes
shutdown -r +5

# Cancel a scheduled shutdown or reboot
shutdown -c

# Reboot the system immediately
reboot

# Force a reboot (bypasses standard shutdown procedures)
reboot -f

# Display the current date and time
date

# Display the date in ISO 8601 format
date --iso-8601

# Display the date and time in ISO 8601 format with nanoseconds
date --iso-8601=ns

# Manually set the system date and time
date -s "02 DEC 2020 12:02:02"

# Change the system's timezone (interactive configuration)
sudo dpkg-reconfigure tzdata

# Display available and current locale settings
locale -a

# Open the locale configuration file for editing (uncomment locales to enable them)
sudo nano /etc/locale.gen

# Generate locale files after editing the configuration
sudo locale-gen
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### CPU

```bash
# Display detailed information about the CPU (model, cores, cache size, etc.)
cat /proc/cpuinfo

# Display a summary of CPU architecture and specifications (e.g., number of CPUs, cores, threads, CPU speed)
lscpu

# Display the number of CPU cores available
nproc
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Memory

```bash
# Display memory usage in kilobytes (default output)
free

# Display memory usage in a human-readable format (e.g., MiB, GiB)
free -h  # or --human

# Display memory usage in a human-readable format using SI units (powers of 1000 instead of 1024)
free -h --si

# Continuously display memory usage, refreshing every 5 seconds
free -s 5  # or --seconds 5

# Display detailed memory information (including total, free, available, and buffers)
cat /proc/meminfo

# Display detailed information about available memory blocks
lsmem

# Display a summary of memory block information (total, usable, offline)
lsmem --summary
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Disk

```bash
# Display disk space usage for all mounted file systems
df

# Display disk space usage for all mounted file systems in a human-readable format (e.g., MiB, GiB)
df -h  # or --human-readable

# Display inode usage for all mounted file systems in a human-readable format
df -ih

# Display disk usage of the current directory and its subdirectories
du

# Display disk usage of a specified directory and its subdirectories
du /path/to/directory

# Display disk usage in a human-readable format (e.g., MiB, GiB)
du -h  # or --human-readable

# Display disk usage of all files and directories in human-readable format (-h), sort the output in reverse numerical order (-rh) to show largest files first
du -ah /path/to/directory | sort -rh | head 

# Display disk usage up to a specified depth level (e.g., 1 level deep)
du -d 1  # or --max-depth=1

# Display the size of the current directory only (without subdirectories)
du -d 0

# Display the total disk usage of the current directory and its subdirectories in a human-readable format
du -sh

# List all block devices (e.g., hard drives, SSDs, partitions) in a tree-like format
lsblk
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Hardware

```bash
# Display kernel log messages (useful for troubleshooting hardware and system issues)
dmesg

# Manage udev devices and events (e.g., trigger or settle device events)
udevadm

# Monitor udev events in real-time (useful for detecting device changes)
udevadm monitor

# Display detailed information about all hardware components (CPU, memory, storage, network, etc.)
lshw

# List all hardware buses (PCI, USB, etc.)
lshw -businfo

# List all PCI devices and their details (e.g., graphics cards, network cards)
lspci

# List all USB devices connected to the system
lsusb
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Network Management

### Network Troubleshooting

```bash
# Send multiple ICMP echo requests (ping) to a specified host (e.g., example.com)
ping example.com

# Send 10 ICMP echo requests to a specified host, with 5-second intervals between each attempt
ping -c 10 -i 5 example.com

# Display detailed information about all active network interfaces
ifconfig

# Display information for all network interfaces, including inactive ones
ifconfig -a

# Display detailed information for a specific network interface (e.g., eth0)
ifconfig eth0

# Enable (activate) the specified network interface (e.g., eth0)
ifconfig eth0 up

# Disable (deactivate) the specified network interface (e.g., eth0)
ifconfig eth0 down

# Assign a specific IP address to a network interface (e.g., eth0)
ifconfig eth0 192.168.120.56

# List all IP addresses assigned to the system's network interfaces
ip addr
ip a

# Display the current routing table and routes to connected networks
ip route
ip r

# Extract the IP address assigned to the eth0 network interface
ip address | grep eth0 | grep inet | awk '{print $2}'

# Retrieve the external IP address of the system using an online service
curl ifconfig.me

# Display statistics and usage information for all network interfaces
netstat -i    # or --interfaces

# List all open ports that are actively listening for connections
netstat -l    # or --listening

# List all listening sockets (TCP, UDP, and Unix sockets)
ss -l

# List listening sockets along with the associated process names and PIDs
ss -tulpn

# Display all TCP connections
ss -t

# Display all UDP connections
ss -u

# Display only listening TCP connections
ss -lt

# Display only listening UDP connections
ss -lu

# Display all established TCP connections
ss -ta state established

# Display network connections sorted by bytes sent/received
ss -t -o state established '(bytcp)'

# Show summary statistics for each protocol (TCP, UDP, etc.)
ss -s

# Display all network connections for a specific port (e.g., port 80)
ss -tulpn | grep :80

# Show all connections and include timestamps
ss -o

# Display all connections with detailed socket options
ss -K

# Trace the route packets take to reach a specified host (e.g., example.com)
traceroute example.com

# Continuously trace the route packets take, showing real-time updates (wide report format)
mtr -w example.com    # or --report-wide

# Generate a detailed report of network traffic over 100 cycles, listing all hops in wide format
mtr -r -w -c 100 example.com    # or --report --report-wide --report-cycles 100

# Scan localhost for the 1000 most commonly used open ports
nmap 0.0.0.0

# Scan all 65,535 possible ports on localhost for open ports
nmap 0.0.0.0 -p1-65535

# Scan a remote IP address (e.g., 192.168.4.3) for the 1000 most common open ports
nmap 192.168.4.3

# Discover all active machines on the network by sending ping requests to each address in the specified subnet
nmap -sP 192.168.1.1/24
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## DNS

```bash
# Display the current DNS resolver configuration, including active nameservers, search domains, and other resolver settings
resolvectl

# Display the status of systemd-resolved, including DNS servers in use
systemctl status systemd-resolved

# Flush the DNS cache using systemd-resolved
resolvectl flush-caches

# Display the contents of the DNS cache
resolvectl statistics

# Display the contents of the system's resolv.conf file, which lists active nameservers
cat /etc/resolv.conf

# Display the configuration file for systemd-resolved, which contains DNS resolver settings
cat /etc/systemd/resolved.conf

# Query DNS information for the specified domain and display A (IPv4) records by default
dig example.com

# Query and display only IPv4 (A) records for the specified domain
dig -4 example.com

# Query and display only IPv6 (AAAA) records for the specified domain
dig -6 example.com

# Query DNS information for the specified domain using a specific nameserver
dig example.com @<nameserver>

# Query DNS information for the specified domain on a custom port (e.g., port 123)
dig example.com -p 123

# Query the NS (Name Server) records for a domain
dig example.com NS

# Query the MX (Mail Exchange) records for a domain
dig example.com MX

# Query the TXT (Text) records for a domain (commonly used for SPF, DKIM, and verification)
dig example.com TXT

# Query all available DNS records for a domain (A, NS, MX, TXT, etc.)
dig example.com ANY

# Perform a simple DNS lookup for a domain
nslookup example.com

# Specify a custom nameserver to use for the query
nslookup example.com <nameserver>

# Interactive mode: allows multiple queries without restarting the command
nslookup
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## HTTP Requests

### curl

```bash
# Return the response body from the specified URL
curl https://example.com

# Return the response body along with the HTTP headers and status code
curl -i https://example.com 

# Follow redirects automatically and return the final response body
curl -L https://example.com

# Download the response body and save it as a file with the same name as on the server
curl -O https://example.com/foo.txt

# Add a custom HTTP header (e.g., User-Agent) to the request
curl -H "User-Agent: Foo" https://example.com

# Send a POST request with JSON data and specify the content type in the header
curl -X POST -H "Content-Type: application/json" -d '{"foo":"bar"}' https://example.com

# Send a POST request with URL-encoded form data
curl -X POST --data-urlencode "foo=bar" https://example.com

# Send a GET request and store the response in a file
curl -o output.txt https://example.com

# Send a request with multiple custom headers
curl -H "Accept: application/json" -H "Authorization: Bearer <token>" https://example.com

# Follow redirects, include headers, and limit maximum time for the request to 10 seconds
curl -L -i --max-time 10 https://example.com

# Upload a file to a server (e.g., using a form)
curl -X POST -F "file=@path/to/file.txt" https://example.com/upload

# Download a file in chunks and resume a previous download if interrupted
curl -C - -O https://example.com/largefile.zip

# Send a PUT request with data
curl -X PUT -d '{"foo":"bar"}' -H "Content-Type: application/json" https://example.com/resource

# Pass authentication credentials (Basic Auth)
curl -u username:password https://example.com

# Send a request via a proxy
curl -x http://proxy.example.com:8080 https://example.com
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### wget

```bash
# Download a file from a specified URL and save it to the current directory
wget https://example.com/file.txt

# Download a file from a specified URL and save it as a file with the specified name
wget -O foo.txt https://example.com/file.txt

# Download multiple files listed in a text file (one URL per line)
wget -i urls.txt

# Resume a partially downloaded file
wget -c https://example.com/largefile.zip

# Download files recursively from a website (use with caution)
wget -r https://example.com

# Limit the download speed to 100 KB/s
wget --limit-rate=100k https://example.com/file.zip

# Mirror an entire website (download all HTML, images, etc.)
wget --mirror --convert-links --page-requisites https://example.com

# Specify a custom User-Agent when downloading a file
wget --user-agent="Mozilla/5.0 (compatible; MyDownloader/1.0)" https://example.com/file.zip

# Download a file using FTP with username and password
wget ftp://username:password@ftp.example.com/file.txt
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Systemd

### systemctl

```bash
# Display the status of the specified unit (e.g., service or socket), showing whether it is active, inactive, or failed
sudo systemctl status <unit>

# Start the specified unit if it is not already running
sudo systemctl start <unit>

# Stop the specified unit if it is currently running
sudo systemctl stop <unit>

# Restart the specified unit by stopping and then starting it
sudo systemctl restart <unit>

# Reload the configuration of the specified unit without restarting it (useful for services that support live reloading)
sudo systemctl reload <unit>

# Enable the specified unit to start automatically at boot
sudo systemctl enable <unit>

# Disable the specified unit from starting automatically at boot
sudo systemctl disable <unit>

# List all currently active units (running services, sockets, timers, etc.)
sudo systemctl list-units

# List all installed service unit files, showing their enablement status (enabled, disabled, static, etc.)
sudo systemctl list-unit-files --type=service

# Open an editor to create or modify a drop-in configuration file for the specified unit
# (This allows custom configurations without altering the main unit file)
sudo systemctl edit <unit>

# Open an editor to directly edit the full unit file for the specified unit
# (Use this only if you need to modify the complete configuration)
sudo systemctl edit --full <unit>

# Reload the systemd manager configuration to apply changes made to unit files
# (Necessary after editing or creating unit files)
sudo systemctl daemon-reload

# Check whether the specified unit is enabled to start at boot
sudo systemctl is-enabled <unit>

# Check whether the specified unit is active (running)
sudo systemctl is-active <unit>

# Mask a unit to prevent it from being started manually or automatically
sudo systemctl mask <unit>

# Unmask a unit, allowing it to be started again
sudo systemctl unmask <unit>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### journalctl

```bash
# View all logs in reverse chronological order (newest entries first)
journalctl

# View logs from the current boot only
journalctl -b

# View logs from a previous boot (-1 is the last boot, -2 is the boot before that, etc.)
journalctl -b -1

# List all recorded boots with their corresponding boot IDs and timestamps
journalctl --list-boots

# Display the disk space currently consumed by journal logs
journalctl --disk-usage

# View kernel logs only
journalctl -k

# Follow logs in real-time (similar to `tail -f`)
journalctl -f

# View logs for a specific service or systemd unit (e.g., sshd or nginx)
journalctl -u sshd
journalctl -u nginx.service

# View logs for a specific user process by user ID (e.g., UID 1000)
journalctl _UID=1000

# View logs with a specific priority level (e.g., error logs only)
journalctl -p err    # 'err' corresponds to priority level 3 (errors)

# View logs from a specific executable (e.g., sshd) or process ID (PID)
journalctl /usr/bin/sshd
journalctl _PID=1234

# View logs with a specific metadata field (e.g., logs from a specific hostname)
journalctl _HOSTNAME=myserver

# View logs from a specific time range
journalctl --since "2024-07-30 00:00:00" --until "2024-07-31 00:00:00"

# View logs since a relative time (e.g., 1 hour ago)
journalctl --since "1 hour ago"

# View logs since the beginning of today
journalctl --since today

# Display logs with detailed metadata for each entry
journalctl -o verbose

# View priority level 3 (errors) logs from the current boot with explanations
journalctl -p 3 -xb

# Show the most recent logs with detailed explanations of errors, warnings, and important messages
journalctl -xe

# Display the disk space currently used by journal logs
journalctl --disk-usage

# Remove old logs, keeping only logs from the last two weeks
journalctl --vacuum-time=2weeks

# Remove old logs, reducing total disk space usage to a maximum of 500 MB
journalctl --vacuum-size=500M
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Scheduled Tasks

### cron

`cron` is a time-based job scheduler in Unix-like operating systems, including Linux. It enables users to schedule scripts or commands to run automatically at specified intervals or times. The scheduled jobs are known as "cron jobs."

```bash
# List the current user's crontab entries
crontab -l

# Edit the current user's crontab using the default file editor
crontab -e

# Load a crontab from a specified file
crontab /path/to/crontab

# Save the current crontab entries to a specified file
crontab -l > /path/to/crontab

# Remove the current user's crontab (deletes all scheduled jobs)
crontab -r

# EXAMPLES

# Run the command every minute
* * * * * <command>

# Run the command every 15 minutes
*/15 * * * * <command>

# Run the command every hour at the start of the hour
0 * * * * <command>

# Run the command daily at 6:15 AM
15 6 * * * <command>

# Run the command every Friday at 4:44 AM
44 4 * * 5 <command>

# Run the command at midnight on the first day of every month
0 0 1 * * <command>

# Run the command at midnight on January 1st every year
0 0 1 1 * <command>
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### at

`at` is used for scheduling one-time tasks to run at a specific time in the future. It is suitable for tasks that do not recur and need to be executed only once.

```bash
# Schedule a job to run at a specific time (2:00 PM today)
echo "sh /path/to/script.sh" | at 14:00

# Schedule a job to run at a specific time on the next day (8:00 AM tomorrow)
echo "sh /path/to/script.sh" | at 8:00 AM tomorrow

# Schedule a job to run after a relative time (1 hour from now)
echo "sh /path/to/script.sh" | at now + 1 hour

# List all scheduled one-time tasks (shows job numbers and scheduled times)
atq

# Remove a scheduled job by its job number (e.g., job number 5)
atrm 5

# List all scheduled one-time tasks (alternative to atq)
at -l

# Display the details of a specific scheduled job by its ID
at -c 1

# Remove a scheduled task by its ID
at -r 1
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### anacron

`anacron` is used for scheduling recurring jobs on systems that may not be running continuously, unlike cron. It ensures jobs run after the system is restarted, even if they were missed.

`anacron` uses a configuration file, typically located at **/etc/anacrontab**, to define scheduled jobs. The syntax is different from cron and does not specify exact times. Instead, it specifies the number of days between job executions and the delay after the system starts.

- **period:** Number of days between job executions (e.g., 1 for daily, 7 for weekly).
- **delay:** Delay (in minutes) before running the job after the system starts.
- **job_identifier:** A unique name for the job (used for logging purposes).
- **command:** The command or script to run.

```bash
# Edit the anacrontab file (system-wide configuration for anacron jobs)
sudo nano /etc/anacrontab

# Example anacron job entries (format: period delay identifier command)

# Run a daily backup job with a 5-minute delay after system startup
1 5 daily_backup /path/to/backup_script.sh

# Run a weekly log cleanup job with a 10-minute delay after system startup
7 10 weekly_log_cleanup /path/to/log_cleanup.sh

# Run a monthly report generation job with a 15-minute delay after system startup
30 15 monthly_report /path/to/report_script.sh
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Terminal Multiplexers

Tmux is terminal multiplexer that allows multiple terminal sessions to be accessed simultaneously in a single window. It enables users to run multiple command-line programs concurrently and detach processes from their controlling terminals, allowing remote sessions to remain active without being visible.

Here’s a handy table of the default **tmux** keyboard shortcuts to reference. These shortcuts assume the default prefix is `Ctrl+b`.

Source: <https://tmuxcheatsheet.com>

### Tmux Cheatsheet

#### Sessions

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `tmux`                                    | Start a new session                                                          |
| `tmux new -s mysession`                   | Start a new session with the name `mysession`n                               |
| `tmux attach`                             | Attach to the last session                                                   |
| `tmux attach -t mysession`                | Attach to a session with the name `mysession`                                |
| `tmux attach -d`                          | Detach others on the session                                                 |
| `tmux rename -t mysession newname`                | Rename a session                                                             |
| `tmux ls` or `tmux list-sessions`         | Show all sessions                                                            |
| `tmux kill-session`                       | Kill/delete the current session                                              |
| `tmux kill-session -t mysession`          | Kill/delete session `mysession`                                              |
| `tmux kill-session -a`                    | Kill/delete all sessions but the current                                     |
| `tmux kill-session -a -t mysession`       | Kill/delete all sessions but `mysession`                                     |
| `Ctrl + b` then `$`                       | Rename session                                                               |
| `Ctrl + b` then `d`                       | Detach from session                                                          |
| `Ctrl + b` then `s`                       | Show all sessions                                                            |
| `Ctrl + b` then `w`                       | Session and window preview                                                   |
| `Ctrl + b` then `(`                      | Move to previous session                                                     |
| `Ctrl + b` then `)`                      | Move to next session                                                         |

---

#### Windows

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `tmux new -s mysession -n mywindow`       | Start a new session with the name `mysession` and window `mywindow`          |
| `Ctrl + b` then `c`                       | Create a new window                                                          |
| `Ctrl + b` then `,`                       | Rename the current window                                                    |
| `Ctrl + b` then `&`                       | Close the current window                                                     |
| `Ctrl + b` then `w`                       | List windows                                                                 |
| `Ctrl + b` then `p`                       | Move to the previous window                                                  |
| `Ctrl + b` then `n`                       | Move to the next window                                                      |
| `Ctrl + b` then `[0-9]`                   | Switch/select window by number                                               |
| `Ctrl + b` then `l`                       | Toggle last active window                                                    |
| `swap-window -s 2 -t 1`                   | Swap window 2 (source) and 1 (destination)                                   |
| `swap-window -t -1`                       | Move current window to the left by one position                              |
| `move-window -s src_ses:win -t target_ses:win` | Move window from source session to target session                          |
| `move-window -r`                          | Renumber windows to remove gaps in the sequence                              |

---

#### Panes

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `Ctrl + b` then `;`                       | Toggle last active pane                                                      |
| `split-window -h` or `Ctrl + b` then `%`  | Split pane horizontally                                                     |
| `split-window -v` or `Ctrl + b` then `"`  | Split pane vertically                                                       |
| `join-pane -s 2 -t 1`                     | Join two windows as panes                                                   |
| `Ctrl + b` then `{`                       | Move the current pane left                                                  |
| `Ctrl + b` then `}`                       | Move the current pane right                                                 |
| `Ctrl + b` then arrow keys                | Switch to pane in the specified direction                                   |
| `setw synchronize-panes`                  | Toggle synchronize-panes                                                    |
| `Ctrl + b` then `Space`                   | Toggle between pane layouts                                                 |
| `Ctrl + b` then `o`                       | Switch to the next pane                                                     |
| `Ctrl + b` then `q`                       | Show pane numbers                                                           |
| `Ctrl + b` then `q` then `[0-9]`          | Switch/select pane by number                                                |
| `Ctrl + b` then `z`                       | Toggle pane zoom                                                            |
| `Ctrl + b` then `!`                       | Convert pane into a window                                                  |
| `Ctrl + b` then `x`                       | Close the current pane                                                      |

---

#### Copy Mode

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `setw -g mode-keys vi`                    | Use vi keys in buffer                                                       |
| `Ctrl + b` then `[`                       | Enter copy mode                                                             |
| `Ctrl + b` then `PgUp`                    | Enter copy mode and scroll one page up                                      |
| `q`                                       | Quit mode                                                                   |
| `g`                                       | Go to the top line                                                          |
| `G`                                       | Go to the bottom line                                                       |
| `h`, `j`, `k`, `l`                        | Move cursor left, down, up, right                                           |
| `w`, `b`                                  | Move cursor forward/backward by word                                        |
| `/` or `?`                                | Search forward/backward                                                    |
| `n`, `N`                                  | Next/previous keyword occurrence                                           |
| `Space`                                   | Start selection                                                             |
| `Esc`                                     | Clear selection                                                             |
| `Enter`                                   | Copy selection                                                              |
| `Ctrl + b` then `]`                       | Paste contents of buffer_0                                                 |
| `capture-pane`                            | Copy entire visible contents of pane to a buffer                            |
| `list-buffers`                            | Show all buffers                                                            |
| `choose-buffer`                           | Show all buffers and paste selected                                         |

---

#### Miscellaneous

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `Ctrl + b` then `:`                       | Enter command mode                                                          |
| `set -g OPTION`                           | Set an option for all sessions                                              |
| `setw -g OPTION`                          | Set an option for all windows                                               |
| `set mouse on`                            | Enable mouse mode                                                           |

---

#### Help

| **Command**                               | **Description**                                                              |
|-------------------------------------------|------------------------------------------------------------------------------|
| `tmux list-keys` or `Ctrl + b` then `?`   | List key bindings                                                           |

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Secure Shell Protocol (SSH)

```bash
# Connect to a remote host using the current username and the default SSH port (22)
ssh <hostname>

# Connect to a remote host using an identity file (private key) for authentication
ssh -i <path_to_key> <hostname>

# Connect to a remote host with a specified username over the default SSH port (22)
ssh <user>@<hostname>

# Connect to a remote host with a specified username over a custom port (e.g., 2222)
ssh <user>@<hostname> -p 2222

# Connect to a remote host using an identity file, specifying a custom port, and enabling verbose output (useful for debugging)
ssh -i <path_to_key> <user>@<host> -p 2222 -v

# Generate a new SSH key pair using the Ed25519 algorithm with an optional comment (e.g., your email)
ssh-keygen -t ed25519 -C <email>

# Start the SSH agent (required to add keys for authentication)
eval "$(ssh-agent)"

# Add the private key to the SSH agent for authentication
ssh-add ~/.ssh/<key>

# Copy the public key to the remote host for passwordless login
ssh-copy-id -i <path_to_key> -p 2222 <user>@<host>

# Start the SSH daemon (sshd) to allow incoming SSH connections
systemctl start sshd

# Restart the SSH daemon (useful after changing configuration)
systemctl restart sshd

# Stop the SSH daemon (disables SSH access to the system)
systemctl stop sshd

# Check the status of the SSH daemon
systemctl status sshd

# Display the system journal logs for the SSH service (shows logs specific to the sshd unit)
journalctl -u ssh
```

Set default user and port in `~/.ssh/config`, so you can just enter the name next time:

```bash
nano ~/.ssh/config
Host name
  User <username>
  Hostname <hostname>
  Port <port>
$ ssh name
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Secure Copy (SCP)

```bash
# Copy a local file to a remote directory
scp /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Copy a file from a remote host to a local directory
scp <username>@<remote_host>:/path/to/remote/file /path/to/local/directory

# Recursively copy an entire local directory to a remote directory
scp -r /path/to/local/directory <username>@<remote_host>:/path/to/remote/directory
# Copy a local file to a remote directory over a custom port (e.g., port 2222)
scp -P 2222 /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Copy a local file to a remote directory using a specific private key for authentication
scp -P 2222 -i ~/.ssh/private_key /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Limit the bandwidth usage for the file transfer to 1000 Kbps (useful for large files on limited networks)
scp -l 1000 /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Enable compression for faster file transfer (useful for transferring large text files or data over slow networks)
scp -C /path/to/local/file <username>@<remote_host>:/path/to/remote/directory
# Preserve file attributes (e.g., modification time, access time, and permissions) during transfer
scp -p /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Show the progress of the file transfer in real-time
scp -v /path/to/local/file <username>@<remote_host>:/path/to/remote/directory

# Combine multiple options: recursive copy with compression and progress display
scp -r -C -v /path/to/local/directory <username>@<remote_host>:/path/to/remote/directory

```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Rsync

```bash
# Synchronise files and directories from a local source to a local destination with archive mode (-a), compression (-z), and verbose output (-v)
rsync -avz /path/to/source/ /path/to/destination/

# Synchronise files and directories from a local source to a remote destination over SSH with archive mode, compression, and verbose output
rsync -avz /path/to/local/files <username>@<remote.server>:/path/to/remote/directory/

# Perform a dry-run (no actual changes) of synchronising files over SSH using a specific private key and port, showing what would be copied
rsync -avzh -e "ssh -i .ssh/<key> -p <port_num>" --dry-run /path/to/local/files <username>@<remote.server>:/path/to/remote/directory/

# Perform a dry-run and delete extraneous files from the destination that are no longer present in the source (--delete option)
rsync -avzh -e "ssh -i .ssh/<key> -p <port_num>" --delete --dry-run /path/to/local/files <username>@<remote.server>:/path/to/remote/directory/

# Synchronise a local directory to a USB drive, preserving file attributes
rsync -avz /home/user/documents/ /media/usb_drive/

# Create an incremental backup using hard links (--link-dest) to avoid copying unchanged files from a previous backup
rsync -avz --link-dest=/previous/backup/ /home/user/ /current/backup/

# Synchronise a local directory while excluding specific directories or files (--exclude option)
rsync -avz --exclude "/home/user/documents/" /home/user/ /media/usb_drive/

# Backup a web directory while excluding a temporary directory and appending a date to the backup folder name
rsync -avz --exclude "/var/www/tmp" /var/www/ /mnt/backups/www_$(date +%Y-%m-%d)

# Copy files or directories with compression (-z) and verbose output (-v)
rsync -zv /file_src /file_dst

# Copy files without overwriting existing files at the destination (--ignore-existing)
rsync -avz --ignore-existing /file_src /file_dst

# Copy a file quickly, only if it has been modified (uses file size and timestamp to detect changes)
rsync -zv /file_src /file_dst
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Shell Profile

- bash - `.bashrc`
- zsh - `.zshrc`

```bash
# Always run ls after cd
function cd {
  builtin cd "$@" && ls
}

# Creates a shortcut 'c' for the clear command
alias c='clear'

# Creates a shortcut 'lh' for the ls -lAh command
alias lh="ls -lAh"

# Prompt user before overwriting any files
alias cp='cp --interactive'
alias mv='mv --interactive'
alias rm='rm --interactive'

# Always show disk usage in a human readable format
alias df='df -h'
alias du='du -h'
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Environment Variables

```bash
# Display all environment variables currently set in the shell
printenv

# Another method to display all environment variables
env

# List all shell variables, functions, and environment variables currently set in the shell
set

# Print the value of the PATH environment variable (contains directories for executable search paths)
echo $PATH

# Example: Set the default editor to nano for the current session
export EDITOR=nano

# Set an environment variable permanently by adding it to your shell configuration file
export VAR_NAME=value

# Apply changes made to the .bashrc file (for bash shell users)
source ~/.bashrc

# Apply changes made to the .zshrc file (for zsh shell users)
source ~/.zshrc

# Display the value of a specific environment variable (in this case, HOME directory path)
echo $HOME

# Display the current shell (bash, zsh, etc.)
echo $SHELL

# Display the current working directory
echo $PWD

# Display the current user
echo $USER

# Display the hostname of the system
echo $HOSTNAME

# Unset (remove) an environment variable
unset VAR_NAME
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

## Scripting

### Variables

```bash
# Initialize a variable <variable_name> with the value 123
<variable_name>=123                

# Initialize an integer variable <variable_name> with the value 123
declare -i <variable_name>=123     

# Initialize a readonly variable <variable_name> with the value 123
declare -r <variable_name>=123     

# Print the value of the variable <variable_name>
echo $<variable_name>

# Print the value of the variable <variable_name> followed by "_suffix"
echo ${<variable_name>}_'suffix'

# Print the value of the variable <variable_name> if it exists; otherwise, print 'default'
echo ${<variable_name>:-'default'}

# Make the variable <variable_name> available to child processes
export <variable_name>

# Remove the variable <variable_name>, making it unavailable to child processes and in the current session
unset <variable_name>
```

### Conditional Statements

#### Boolean Operators

- `$<variable>` - Is true
- `!$<variable>` - Is false

#### Numeric Operators

- `-eq` - Equals
- `-ne` - Not equals
- `-gt` - Greater than
- `-ge` - Greater than or equal to
- `-lt` - Less than
- `-le` - Less than or equal to
- `-e` <file> - Check file exists
- `-z` <var> - Check if variable exists

#### String Operators

- `=` - Equals
- `==` - Equals
- `-z` - Is null
- `-n` - Is not null
- `<` - Is less than in ASCII alphabetical order
- `>` - Is greater than in ASCII alphabetical order

#### If Statements

```bash
if [[ $<variable> = '<value1>' ]]; then
  echo 'one'
elif [[ $<variable> = '<value1>' ]] || [[ $<variable> = '<value2>' ]]; then
  echo 'two'
elif [[ $<variable> = '<value3>' ]] && [[ $USER = '<user_name>' ]]; then
  echo 'three'
else
  echo 'four'
fi

# Inline If Statements

[[ $USER = '<user>' ]] && echo 'yes' || echo 'no'
```

#### While Loops

```bash
[
declare -i counter
counter=10
while [$counter -gt 2]; do
  echo The counter is $counter
  counter=counter-1
done
]
```

#### For Loops

```bash
for i in {0..10..2}
  do
    echo "Index: $i"
  done

for filename in file1 file2 file3
  do
    echo "Content: " >> $filename
  done

for filename in *;
  do
    echo "Content: " >> $filename
  done
```

#### Case Statements

```bash
echo "What's the weather like tomorrow?"
read weather

case $weather in
  sunny | warm ) echo "Nice weather: " $weather
  ;;
  cloudy | cool ) echo "Not bad weather: " $weather
  ;;
  rainy | cold ) echo "Terrible weather: " $weather
  ;;
  * ) echo "Don't understand"
  ;;
esac
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)

### Functions

```bash
#!/bin/bash

greet() {
  local world="World"
  echo "$1 $world"
  return "$1 $world"
}
greet "Hello"
greeting=$(greet "Hello")
```

### Exit Codes

```bash
# Exit the script with a success status (0 indicates successful execution)
exit 0

# Exit the script with a failure status (non-zero values indicate errors; 1 is a common error code)
exit 1

# Print the last exit code (useful for checking the success or failure of the previous command)
echo $?
```

[⬆ ʀᴇᴛᴜʀɴ ᴛᴏ ᴄᴏɴᴛᴇɴᴛꜱ](#contents)
</details>
