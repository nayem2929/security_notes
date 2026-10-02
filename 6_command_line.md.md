**Windows Command Line**:
Basic system info commands:
- `set`: to check the commands in the windows path.
- `ver`: to check the windows version.
- `systeminfo`: information about the system
- `more`: can be used to page the output
- `help`: provides helpful information about the command
- `cls`: clears the prompt screen
**Networking**:
- `ipconfig`: shows basic network information like IP address, subnet mask, and default gateway. 
	- using `ipconfig /all` shows more details like DNS and DHCP status.
- `ping X.X.X.X`: Sends am ICMP package and awaits response.
- `tracert X.X.X.X`: Tracks packets as they jump through different routers and switches on the internet.
- `nslookup exmample.com`: Shows the IP address of a domain.
- `netstat`: Can be used to view established connections and listening ports. 
**File and Disk Management:**
- `cd`: change directories with `cd XXX` or simply use as the windows equivalent of `pwd` when used by itself.
- `dir`: print subdirectories.
	- use `dir /a` to print hidden directories.
	- use `dir /s` to print names of files in the current directory and their subdirectories. 
- `tree`:  can be used to neatly print the file tree (All directories and subdirectories).
- `mkdir` and `rmdir`: to make and remove directories respectively.
- `type`: print text files in the CLI.
- `more`: view text files with multiple pages worth of content.
- `copy`: used to make copies of files.
- `move`: used to move or rename files.
- `del` or `erase`: used to remove files.
**Task and Process Management:**
- `tasklist`: to view all ongoing processes.
- `tasklist /FI "imagename eq sshd.exe"`: to find any task related to sshd.
- `taskkill /PID XXXX`: Kills target process.
**Special notes:**
- `/?` can be used with most commands to display a help page.

**Windows PowerShell**:
PowerShell is a powerful tool from Microsoft designed for task automation and configuration management.
PowerShell commands are known as `cmdlets` (Pronounced command-lets).
Commands follow a syntax of Verb-Noun. For example, `Get-Content` retrieves (gets) the contents of a file and outputs it onto the console. Some basic commands are:
- `Get-Command`: Shows the list of all available `cmdlets`.
- `Get-Help`: Like man-page for PS.
- `Get-Alias`: Shows list of all aliases.
- `Find-Module`: Used to find `cmdlets`.
- `Install-Module`: Used to install `cmdlets`.
Commands for navigating the File System:
- `Get-ChildItem`: Just like `dir` in windows CLI or `ls` in Linux.
- `Set-Location`: Works like `cd`.
- `New-Item`: Used to make directories and files.
- `Remove-Item`: To delete files and directories.
- `Copy-Item`: Copies an item.
- `Move-Item`: Moves an Item.
- `Get-Content`: Like `cat`.
Commands for filtering and sorting data:
- `Sort-Object`: Can be used with parameters like Length, Name, etc. to sort accordingly.
- `Where-Object`: Used to find objects with specific conditions.
	- Example: `Get-ChildItem|Where-Object -Property "Extension" -eq ".txt"`
	- The above command pipes all items in the current directory onto the `Where-Object` command. This command then filters the files by the`"Extension"`property, ensuring that only files with extension equal(`-eq`) to`.txt`are listed.
	- There are other comparison operators like `-ne` for "not equal", `-gt` for "greater than", `le`for "less than or equal to", etc.
	- `Get-ChildItem|Where-Object -Property "Name" -like "ship"`will find all objects with the word "ship" in the name.
- `Select-Object`: It's used to select specific properties from objects or limit the number of objects returned.
	- Example: `Get-ChildItem | Select-Object Name,Length` will print only the name and length of the objects.
- `Select-String`: Similar to Linux `grep` or Windows Command Prompt's `findstr`.
	- Example: `Select-String -Path ".\captain-hat.txt" -Pattern "hat"`
	- The above command find the line that contains the word "hat". 
	- `Select-String` also supports  [[4_regex.md|regex]]
System and Network Information related commands:
- `Get-ComputerInfo`: Produces a detailed snapshot of the system configuration. Big brother of `systeminfo`.
- `Get-LocalUser`: Lists all local user accounts on the system.
- `Get-NetIPConfiguration`: Detailed information about the network interfaces on the system.
- `Get-NetIPAddress`: Shows details for all IP addresses configured on the system.
Real-time System Analysis:
- `Get-Process`: provides a detailed view of all currently running processes and important information about them.
- `Get-Service`: allows the retrieval of information about the status of services on the machine, such as which services are running, stopped, or paused.
- `Get-NetTCPConnection` displays current TCP connections, giving insights into both local and remote endpoints.
- `Get-FileHash`: is a useful cmdlet for generating file hashes.
- `Get-Item -Path "C:\House\house_log.txt" -Stream *`: Can be used to view the ADS of any file.
Scripting:
- `Invoke-Command`: Allows execution of code in a remote system. 