# File System Watcher 
A PowerShell script is designed to monitor a specific directory ('C:\FIM') for changes to '.txt' files and report these changes in real-time.

## Utilities 
- PowerShell

## Environment 
- Windows 10

## Script
![image](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/323c2f81-d1f0-4afe-ac2f-da4dc5bd878a)

## Breakdown
- Clear-Host: clears the PowerShell console window to remove any previous output.
- $folderToMonitor: the directory to be monitored
- $filter: set to .txt, the scrip will monitor all text files in the directory
- System.IO.FileSystemWatcher object ($watcher): watches specified directory for changes to .txt files.
- IncludeSubdirectories $false: no subdirectories
- EnableRaisingEvents: starts monitoring immediately upon creation
- $action: defines custome responses to different types of file changes (change, create, delete, renamed).
- Register-ObjectEvent: reacts and subscribes to file change events mentioned above in coordination with each $action event.
  *The script is designed to run without stopping, o/e i.e. continues to execute and respond to events asynchronously - allowing other commands to be executed while continuous monitoring is active. 

## Demonstration
- Before Running Script
![FSW 1](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/99b87ea1-7810-46fc-b126-d2d8cb0dcbeb)

- Script Run
![FSW 2](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/0b62ad11-4b9d-412e-9784-84f7bd3d75b2)


- File Moved to Sample FIM Folder
![FSW 6](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/6a08419c-5a32-4902-83ce-18dd01b393b4)

- File Moved Back to FIM Folder
![FSW 7](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/3847d158-4019-493e-b997-9ba4a91999e1)

- File hello.txt renamed to this is changed.txt
![FSW 8](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/e3d8a49e-66d6-4153-a898-0a5dc681ee4a)

- File has been modified
![FSW 5](https://github.com/JanGuiao/FileSystemWatcher/assets/95273542/4006b2a0-c2fc-4181-a16b-a61e9052e1cf)


