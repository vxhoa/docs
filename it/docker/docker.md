[TOC]

# Docker
## Common commands
### Managing images and containes
* Deleting all containers
```
docker rm $(docker ps -a -q)
```

### Get IP address of a running container
``docker inspect --format '{{.NetworkSettings.Networks.nat.IPAddress}}' [CONTAINER ID OR NAME]``
__Note__: work only in Powershel not Command Prompt


## Docker on Windows
### Useful images
* Windows Server core
https://hub.docker.com/_/microsoft-windows-servercore
   * 2016: ``docker pull microsoft/windowsservercore:ltsc2016``
   * 2019: ``docker pull mcr.microsoft.com/windows/servercore:ltsc2019``
* Microsoft SQL Server Express
https://hub.docker.com/r/microsoft/mssql-server-windows-express/


### Legacy Docker Toolbox
* Create a virtual disk
``docker-machine create -d virtualbox --virtualbox-disk-size "100000" default``
* Resize a virtual disk (only compatiable with vdi extension, use Oracle Virual Box to clone disk to vdi format)
``docker-machine vboxmanage modifymedium docker-vm.vdi --resize 100000``
   * https://medium.com/@suraiya.vic/increasing-virtual-disk-space-for-virtualbox-624c43805f6
   * http://thenerdydeveloper.com/2019/04/06/how-to-resize-virtualbox-hard-disk-size-in-windows/

## Docker on Linux
