# Citypluse-Thammiksha

This repository documents basic command-line tasks using Windows PowerShell. It includes commands for removing directories, deleting files and folders recursively, renaming files, checking disk usage, managing file permissions, and listing running processes.

## Task 1: Remove Directories

Use `mkdir` to create a directory and `rmdir` to remove an empty directory.

**Commands:**

powershell
mkdir temp-dir
rmdir temp-dir


**Explanation:**
- `mkdir` – Creates a new directory.
- `rmdir` – Removes an empty directory.

![Removing an empty directory](homework/task1.png)

## Task 2: Remove Files and Folders Recursively

Use `mkdir` to create a directory, `New-Item` to create a file, and `Remove-Item -Recurse` to remove a directory containing files.

**Commands:**

powershell
mkdir test
New-Item test/data.txt -ItemType File
Remove-Item test -Recurse


**Explanation:**
- `mkdir` – Creates a directory.
- `New-Item` – Creates a new file.
- `Remove-Item -Recurse` – Removes a directory and all its contents recursively.

![Removing files and folders recursively](homework/task2.png)

## Task 3: Rename Files and Check Disk Usage

### Rename a File

Use `New-Item` to create a file and `Rename-Item` to rename it.

**Commands:**

powershell
New-Item old.txt -ItemType File
Rename-Item old.txt new.txt
dir


**Explanation:**
- `New-Item` – Creates a new file.
- `Rename-Item` – Renames a file.
- `dir` – Displays files and directories.

### Check Disk Usage

Use `Get-PSDrive` to check used and free disk space.

**Commands:**

powershell
Get-PSDrive C


To calculate the total size of files in the current directory and its subdirectories:

powershell
Get-ChildItem . -Recurse | Measure-Object -Property Length -Sum


**Explanation:**
- `Get-PSDrive C` – Displays used and free space on the C drive.
- `Get-ChildItem -Recurse` – Lists files and folders recursively.
- `Measure-Object` – Calculates the total file size.

![Renaming files and checking disk usage](homework/task3.png)

## Task 4: File Permissions

File permissions control who can access and modify files.

Use `icacls` to grant and check file permissions in Windows PowerShell.

### Create a File

powershell
New-Item sample.txt -ItemType File


### Grant Permissions

powershell
icacls sample.txt /grant Everyone:F


### Check File Permissions

powershell
icacls sample.txt


**Explanation:**
- `New-Item` – Creates a new file.
- `icacls` – Displays or modifies file permissions.
- `/grant` – Grants permissions to a specified user or group.
- `Everyone:F` – Grants