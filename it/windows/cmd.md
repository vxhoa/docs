# Windows CMD
## Common Windows commands
### File operations
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
### Monitoring
* Removing the whole folder quickly
* tasklist