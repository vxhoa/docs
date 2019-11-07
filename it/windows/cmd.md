# Windows CMD
## Common Windows commands
### System
* Get all computer information
``systeminfo``
* List all started Windows Service
``Net Start``

### IO operations
* List directory content
``dir``
* Create hierachical tree for folder structure
``tree``
* Removing the whole folder quickly
```
Rmdir [FOLDER_PATH] /S /Q
```
* Delete long folders and files
   * Create an empty folder, for example C:\EmptyFolder
   * Open a Windows Command Prompt as an Administrator
   * Type the following command, replacing the example paths with yours
   ```
   Robocopy C:\EmptyFolder [FOLDER TO BE DELETED] /purge
   ```

### Networking
```
Net Use [DISK_LETTER]: \\[NETWORK_PATH] /user:[USERNAME] [PASSWORD] /P:Yes
```

### Monitoring
* Removing the whole folder quickly
* tasklist

### Others
