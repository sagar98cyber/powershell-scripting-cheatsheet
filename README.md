# powershell-scripting-cheatsheet
<!---
[Reference Lecture 1](https://youtu.be/I4SFymp1dcE?t=16)
--->

##  Basics of PowerShell Scripting
Beginning with the basics of the PowerShell
<br>

``` 
    $PSVersionTable
```
> The First command that we have is: [here](./Lecture_1/1_PowerShellVersion.png)<br>
> Displays details about the version of PowerShell that is running in the current session.

<br>

``` 
    Get-Process
```
> The Output for the same is [here](./Lecture_1/2_Get-Process.png)<br>
> Displays details about all the processes currently running on the system.
> This is a cmdlet

<br>

``` 
    Get-Service
```
> The Output for the same is [here](./Lecture_1/3_GET-SERVICE.png)<br>
> Displays details about all the services currently on the system and their state whether they are running or stopped.
> For Example: [Background Intelligent File Transfer Service](./Lecture_1/4_file_transfer.png) is used for file transfer<br>
> This is a cmdlet

<br>

``` 
    Get-Date
```
> The Output for the same is [here](./Lecture_1/5_getDate.png)<br>
> Displays the current Date and Time
> This is a cmdlet

<br>

``` 
    Get-ChildItem
```
> The Output for the same is [here](./Lecture_1/6_getChildItem.png)<br>
> Displays all the current files and directories of the current working directory, just like a *'cd'* or a *'ls'* command
> This is a cmdlet
<br>

#### If noticed carefully the *Get-ChildItem* cmdlet works exactly like the *'dir'*,*'ls'*. So why we have all the three of them?🤔
>*Get-ChildItem* is a cmdlet, whereas *'dir'*,*'ls'* are its aliases. Aliases are nothing but the identifier to the cmdlets.<br>
>We create Aliases for our ease to remember any specific cmdlet with our identifiers.<br>
>We use  *Get-Alias* command to display all the aliases present on the current system.
``` 
    Get-Alias
```
> The Output for the same is [here](./Lecture_1/7-dir-GetChildItem.png)<br>
> The output shows o/p of 2 commands the first one is cmdlet and the second is alias 
