# Winrm
Simple winrm shell written in ruby for linux.

WinRM is enabled by default on all Windows Server operating systems (since Windows Server 2012 and above), but disabled on all client operating systems like Windows 10, Windows 8 and Windows 7.

To let a user to connect to a remote machine through WinRM, it’s enough to be a member of the built-in local group of administrators or Remote Management Users security group (this group is created by default starting from PowerShell 4.0). This group also has access to WMI resources via management protocols (e.g., WS-Management)

By default WinRM HTTP uses port 80.  On Windows 7 and higher the default port is 5985.
By default WinRM HTTPS uses port 443.  On Windows 7 and higher the default port is 5986.

The included code will create a powershell remote session on the targeted system.

This requires having a username and password on the domain. An example attack would look like this.

1. Perform nmap and find system with winrm enabled.
2. Perform password spraying attack or get hashes with responder.
3. Plug credentials into the shell.
4. Run shell with ruby winrm_shell.rb 
