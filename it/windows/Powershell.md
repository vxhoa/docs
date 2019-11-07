# Windows Powershell
## Common powershell command
### Get-WindowsFeature
* Example 1
``Get-WindowsFeature`
This example returns all available features.
* Example 2
``Get-WindowsFeature -Name AD*, Web*``
This example returns a list of available and installed features that have a command ID starting with AD or Web.

### Install-WindowsFeature
* Example 1
``Install-WindowsFeature Web-Ftp-Server``
This example install FTP Server


### Create an user
``Net User [USER_NAME] [PASSWORD] /ADD``

### Add an user into a group
``Net localgroup [GROUP_NAME] [USER_NAME] /ADD``