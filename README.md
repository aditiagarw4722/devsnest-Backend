# devsnest-Backend

<h4>How to set up WSL!
To install Redis Windows Subsystem for Linux, follow the instructions on Microsoft Docs. The short version is: In Windows 10, Microsoft replaces Command Prompt with PowerShell as the default shell. Open PowerShell as Administrator and run this command to enable Windows Subsystem for Linux (WSL):
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
Reboot Windows after making the change—note that you only need to do this one time.</h4>
<h1>Download and install one of the supported Linux distros from the Microsoft Store.
Ubuntu 18.04 (installs Redis v4.09)
Debian GNU/Linux (installs Redis v3.2.6)
Install and Test Redis</h1>
<h3>Launch the installed distro from your Windows Store and then install redis-server. The following example works with Ubuntu (you’ll need to wait for initialization and create a login upon first use):</h3>
<br />
> sudo apt-get update
> <br />
> <h1>sudo apt-get upgrade</h1>
> <br />
> sudo apt-get install redis-server
> <br />
> redis-cli -v
> <br />
<h2>Restart the Redis server to make sure it is running:</h2>
<br />
> sudo service redis-server restart
> <br>
Execute a simple Redis command to verify your Redis server is running and available:
$ redis-cli <br>
127.0.0.1:6379> set user:1 "Jane"
127.0.0.1:6379> get user:1
"Jane"
<br>
<h2>To stop your Redis server:</h2>
<br>
> sudo service redis-server stop
