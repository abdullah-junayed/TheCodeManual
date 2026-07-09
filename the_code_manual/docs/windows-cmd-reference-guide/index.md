# 1\. General & UI Commands

**HELP** - Provides detailed information and usage instructions for specific Windows commands.

_Syntax:_ HELP \[command\]

_Example:_ help cls

**COLOR** - Changes the terminal's foreground and background text colors.

_Syntax:_ COLOR \[attr\]

_Example:_ color a (Sets terminal text to light green)

**PROMPT** - Changes the cmd.exe command prompt display text.

_Syntax:_ PROMPT \[text\]

_Example:_ prompt user@hacker\$G (Changes prompt to user@hacker>)

**TITLE** - Sets the window title for the current Command Prompt session.

_Syntax:_ TITLE \[string\]

_Example:_ title Windows CMD Reference

**F7 (Keyboard Shortcut)** - Opens a pop-up menu containing the command history for the current session. Allows quick navigation and execution of previous commands using arrow keys.

**CLIP (Pipe)** - Redirects the output of a command directly to the Windows clipboard for easy pasting.

_Syntax:_ \[command\] | clip

_Example:_ ipconfig | clip

# 2\. File & Directory Management

**DIR** - Displays a list of files and subdirectories in the current or specified directory.

_Syntax:_ DIR \[drive:\]\[path\]\[filename\]

_Example:_ dir /w

**CD (CHDIR)** - Displays the name of, or changes, the current working directory.

_Syntax:_ CD \[path\]

_Example:_ cd \\learn_cmd

**MKDIR / MD** - Creates a new directory. MD can also be used to create directories with Windows reserved names (e.g., con, aux) under specific contexts.

_Syntax:_ MKDIR \[drive:\]path

_Example:_ mkdir my_folder  
md con\\

**RMDIR** - Deletes a directory. Using the /S switch forcefully deletes an entire folder along with all files and subfolders inside it.

_Syntax:_ RMDIR /S \[drive:\]path

_Example:_ rmdir /s folder1

**COPY** - Copies one or more files safely from one location to another.

_Syntax:_ COPY \[source\] \[destination\]

_Example:_ copy "Document.txt" "C:\\Users\\Username\\Desktop\\"

**DEL** - Permanently deletes a specific file without sending it to the Recycle Bin.

_Syntax:_ DEL \[filename\]

_Example:_ del "Document.txt"

**ATTRIB** - Displays or changes file attributes (e.g., hidden, read-only, system).

_Syntax:_ ATTRIB \[+R | -R\] \[+A | -A\] \[+S | -S\] \[+H | -H\] \[filename\]

_Example:_ attrib +h +r +s "secret_file.txt"

# 3\. System Information & Management

**SYSTEMINFO** - Generates a comprehensive overview of the OS version, RAM capacity, motherboard specifications, and system uptime.

_Example:_ systeminfo

**TASKLIST** - Displays a live list of all active background processes and applications.

_Example:_ tasklist

**TASKKILL** - Forcefully shuts down a program using its Process ID (PID) or image name.

_Syntax:_ TASKKILL /F /PID \[number\]

_Example:_ taskkill /f /pid 5400

**SFC (System File Checker)** - Triggers the System File Checker to automatically scan and repair corrupt Windows operating files. Requires Administrator mode.

_Syntax:_ sfc /scannow

_Example:_ sfc /scannow

**WMIC** - Displays installed software and system components.  
<br/>Note: WMIC is deprecated in newer Windows versions (e.g., Windows 11 24H2). To enable it, run PowerShell as Administrator and execute:  
Add-WindowsCapability -Online -Name WMIC~~~~

_Syntax:_ wmic product get name

_Example:_ wmic product get name

# 4\. Network Diagnostics

**IPCONFIG** - Displays current IP address and network adapter information. Can also be used to clear the DNS cache to fix browsing glitches.

_Example:_ ipconfig  
ipconfig /flushdns

**PING** - Tests the connection to a live website or local IP address to verify if it is reachable.

_Syntax:_ PING \[destination\]

_Example:_ ping google.com  
ping cloudflare.com

**TRACERT** - Traces the exact route data packets take from the local machine to a target server.

_Syntax:_ TRACERT \[destination\]

_Example:_ tracert google.com