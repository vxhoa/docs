[TOC]

# Windows Powershell
## Common powershell command
### File Operations

### Windows Features
#### Get-WindowsFeature
* Example 1: Get all available features
``Get-WindowsFeature``
* Example 2
``Get-WindowsFeature -Name AD*, Web*``
This example returns a list of available and installed features that have a command ID starting with AD or Web.

#### Install-WindowsFeature
* Example 1
``Install-WindowsFeature Web-Ftp-Server``
This example install FTP Server
* Example 2: Enable remote IIS management
```
Install-WindowsFeature Web-Mgmt-Service;
New-ItemProperty -Path HKLM:\software\microsoft\WebManagement\Server -Name EnableRemoteManagement -Value 1 -Force;
```

### Managing user and group
#### Create an user
``Net User [USER_NAME] [PASSWORD] /ADD``
#### Add an user into a group
``Net localgroup [GROUP_NAME] [USER_NAME] /ADD``

### IIS
* Create web virual directory
```
New-WebVirtualDirectory -Site '[SITE_NAME]' -Name SAG -PhysicalPath [PHYSICAL_PATH];
```
* Create a FTP Server site
```
C:\WINDOWS\system32\inetsrv\appcmd.exe Set Config 'Default Web Site' -section:system.webServer/directoryBrowse /enabled:"True" /showFlags:'Date, Time, Size, Extension';
```
### Others
