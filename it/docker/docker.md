[TOC]

# Docker

## Common commands

### Get IP address of a running container
``docker inspect --format '{{.NetworkSettings.Networks.nat.IPAddress}}' [CONTAINER ID OR NAME]``
__Note__: work only in Powershel not Command Prompt

### Managing images, containes and other resources
#### Image
* Delete all images
``docker rmi $(docker images -a -q)``
* List all docker images
``docker images -a``
* Remove dangling images
Docker images consist of multiple layers. Dangling images are layers that have no relationship to any tagged images. They no longer serve a purpose and consume disk space. They can be located by adding the filter flag, -f with a value of dangling=true to the docker images command. When you’re sure you want to delete them, you can use the docker images purge command:
``docker images -f dangling=true``

#### Container
* Inspect a container
``docker inspect [NAME OR ID]``
* Stop all containers
``docker stop $(docker ps -a -q)``
* Remove all existed containers
    ``docker rm $(docker ps -a -f status=exited -q)``
* Remove all containers
``docker rm $(docker ps -a -q)``

#### Resource
* Cleaning up any resources — images, containers, volumes, and networks — that are dangling (not associated with a container)
``docker system prune``
* To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the commamd
``docker system prune -a``
* Remove dangling volumes
Since the point of volumes is to exist independent from containers, when a container is removed, a volume is not automatically removed at the same time. When a volume exists and is no longer connected to any containers, it’s called a dangling volume. To locate them to confirm you want to remove them, you can use the docker volume ls command with a filter to limit the results to dangling volumes. When you’re satisfied with the list, you can remove them all with docker volume prune:
``docker volume ls -f dangling=true``

## Docker on Windows
### IIS Remote Management for Docker Containers
https://devblogs.microsoft.com/premier-developer/iis-remote-management-for-docker-containers/

### Docker Desktop for Windows
Check release notes and download at https://docs.docker.com/docker-for-windows/release-notes/

__Default resource limits for Windows vs Linux containers__:
https://www.sqlservercentral.com/blogs/default-resource-limits-for-windows-vs-linux-containers-in-docker-desktop

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
