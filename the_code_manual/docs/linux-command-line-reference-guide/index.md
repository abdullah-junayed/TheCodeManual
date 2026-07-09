# How to Read This Guide

Welcome to Linux! Don't let the text-based terminal scare you. Think of it as a super-fast way to talk directly to your computer without using a mouse. Every command follows a simple pattern:

command -options arguments

**• Command:** The action word (What you want to do).  
**• Options (Flags):** Extra settings that tweak how the command behaves (usually starts with a dash '-').  
**• Arguments:** The target (What folder, file, or website you are running the command on).

# Phase 1: Basic Survival (Moving & Looking Around)

Just like opening your file explorer, these commands help you see where you are and navigate folders.

## pwd (Print Working Directory)

**• GUI Analogy:** Like Where am I?.  
**• Explanation:** Shows you the exact folder pathway you are standing in right now.
```bash
\$ pwd
```
## ls (List)

**• GUI Analogy:** Like Open a folder visually.  
**• Explanation:** Lists all files and folders in your current location. Use '-la' to see secret/hidden files.
```bash
\$ ls -la
```
## cd (Change Directory)

**• GUI Analogy:** Like Double-click a folder.  
**• Explanation:** Moves you into another folder. Use 'cd ..' to go backward one step.

`\$ cd /var/log`

## clear (Clear Screen)

**• GUI Analogy:** Like Wipe the whiteboard.  
**• Explanation:** Wipes your terminal screen clean if it gets too cluttered.

```bash
\$ clear
```

## history (History)

**• GUI Analogy:** Like Time machine logs.  
**• Explanation:** Shows a list of every single command you have typed in this session.
```bash
\$ history
```
## The man and help command
You use the man and help commands in Linux to find documentation, syntax, and options for terminal commands directly from the command line without an internet connection.

- **`man` (Manual)** provides exhaustive, deeply detailed documentation for standalone applications, system files, and external tools.
- **`help` (Shell Help)** provides quick, concise summaries specifically for commands that are built directly into the command-line shell (like Bash)

Example:
```bash
man touch (In touch, you can use that tool/command you are search about.)
```
```bash
help cd (In cd, you can use that tool/command you are search about.)
```


# Phase 2: The File Manager (Creating & Deleting Files)
Commands to create, copy, move, rename, and delete things without using a mouse.
## mkdir (Make Directory)

**• GUI Analogy:** Right click -> Create New Folder.  
**• Explanation:** Creates a completely brand-new, empty folder.
```bash
\$ mkdir my_new_folder
```
## touch (Touch)

**• GUI Analogy:** Right click -> New Text Document.  
**• Explanation:** Creates a blank new file instantly.
```bash
\$ touch index.html
```
## cp (Copy)

**• GUI Analogy:** Ctrl + C then Ctrl + V.  
**• Explanation:** Copies files or folders. Use '-r' if you are copying a folder with items inside it.
```bash
\$ cp file.txt copy_file.txt
```
## mv (Move / Rename)

**• GUI Analogy:** Drag & Drop or Rename.  
**• Explanation:** Moves a file to a new location, or renames it if kept in the same folder.
```bash
\$ mv old_name.txt new_name.txt
```
## rm (Remove)

**• GUI Analogy:** Shift + Delete (No Recycle Bin!).  
**• Explanation:** Permanently deletes a file or folder. Warning: There is no undo! Use '-rf' carefully to force-delete folders.
```bash
\$ rm -rf trash_folder
```
## tree (Tree View)

**• GUI Analogy:** Expanding folders in a side panel.  
**• Explanation:** Displays a beautiful visual map of your folders and sub-folders.
```bash
\$ tree
```
# Phase 3: Text Detectives (Looking inside Files)

Instead of opening heavy apps like Notepad, use these commands to read and search text instantly.

## cat (Concatenate)

**• GUI Analogy:** Quick preview.  
**• Explanation:** Dumps the entire content of a file directly onto your screen.
```bash
\$ cat config.json
```
## less (Less is More)

**• GUI Analogy:** Opening a clean reader app.  
**• Explanation:** Opens a file in an interactive view. You can scroll up and down. Press 'q' to exit.
```bash
\$ less system.log
```
## head (Head)

**• GUI Analogy:** Reading the top headline.  
**• Explanation:** Shows you just the very first 10 lines of a file.
```bash
\$ head -n 10 entries.txt
```
## tail (Tail)

**• GUI Analogy:** Watching live updates.  
**• Explanation:** Shows you the last 10 lines of a file. Use '-f' to stream new logs live as they happen.
```bash
\$ tail -f access.log
```
## grep (Global Regular Expression Print)

**• GUI Analogy:** Ctrl + F (Find Text).  
**• Explanation:** Searches through files to find lines matching a keyword you type.
```bash
\$ grep "ERROR" server.log
```
## wc (Word Count)

**• GUI Analogy:** Document properties.  
**• Explanation:** Counts lines, words, and characters inside a file.
```bash
\$ wc -l script.py
```
# Phase 4: System Diagnostics (Checking PC Health)

How to check your hardware, free RAM memory, and hard drive storage limits.

## free (Free Memory)

**• GUI Analogy:** Task Manager -> Performance -> RAM.  
**• Explanation:** Shows how much RAM memory your system has left.
```bash
\$ free -h
```
## df (Disk Free)

**• GUI Analogy:** Looking at 'This PC' drive capacities.  
**• Explanation:** Shows your hard drive partitions and how much GB storage is left.
```bash
\$ df -h
```
## du (Disk Usage)

**• GUI Analogy:** Checking file/folder properties size.  
**• Explanation:** Calculates exactly how much space a specific folder is taking up on disk.
```bash
\$ du -sh /var/log
```
## uname (Unix Name)

**• GUI Analogy:** System Properties screen.  
**• Explanation:** Displays your kernel version and whether you are running 64-bit Linux.
```bash
\$ uname -a
```
## htop (Interactive Process Viewer)

**• GUI Analogy:** Task Manager Processes Tab.  
**• Explanation:** A colored, live dashboard showing CPU, RAM, and every running app. Press 'q' to quit.
```bash 
\$ htop
```
# Phase 5: Permissions & Power (Who rules the PC?)

Linux is highly secure. You must explicitly tell the computer if you are acting as an administrator.

## whoami (Who Am I?)

**• GUI Analogy:** Checking active profile user.  
**• Explanation:** Prints the name of the user account you are logged into right now.
```bash
\$ whoami
```
## sudo (SuperUser Do)

**• GUI Analogy:** Right click -> Run as Administrator.  
**• Explanation:** Forces the command to execute with absolute root administrative power.
```bash
\$ sudo apt update
```
## chmod (Change Mode)

**• GUI Analogy:** File Security -> Properties -> Permissions.  
**• Explanation:** Changes who is allowed to Read, Write, or Execute a script.
```bash
\$ chmod +x script.sh
```
## chown (Change Owner)

**• GUI Analogy:** Reassigning file ownership keys.  
**• Explanation:** Changes which specific user or group owns a file.
```bash
\$ sudo chown john:john data.csv
```
# Phase 6: Web & Apps (Internet & Installations)

How to download web files, verify connection speeds, and install programs.

## ping (Packet Internet Groper)

**• GUI Analogy:** Testing Wi-Fi connection bars.  
**• Explanation:** Sends a ping to a domain to check if your internet or server is online.
```bash
\$ ping -c 4 google.com
```
## curl (Client URL)

**• GUI Analogy:** Invisible Web Browser.  
**• Explanation:** Downloads content or code headers directly from web URLs onto your terminal.
```bash
\$ curl -I <https://example.com>
```
## wget (Web Get)

**• GUI Analogy:** Browser Downloader Manager.  
**• Explanation:** Downloads full files, ZIPs, or installations straight from web links.
```bash
\$ wget <https://example.com/file.zip>
```
## ssh (Secure Shell)

**• GUI Analogy:** Remote Desktop Connection (RDP).  
**• Explanation:** Securely connects you to another Linux machine across the globe via terminal.
```bash
\$ ssh user@remote_ip
```
## apt / dnf (Package Managers)

**• GUI Analogy:** App Store / Google Play Store.  
**• Explanation:** Installs, updates, and deletes software tools on your Linux machine cleanly.
```bash
\$ sudo apt install git
```