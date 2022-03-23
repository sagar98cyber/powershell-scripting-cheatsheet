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

#### If you have noticed carefully the *Get-ChildItem* cmdlet works exactly like the *'dir'*,*'ls'*.<br> So why we have all the three of them?🤔
>*Get-ChildItem* is a cmdlet, whereas *'dir'*,*'ls'* are its aliases. Aliases are nothing but the identifier to the cmdlets.<br>
>We create Aliases for our ease to remember any specific cmdlet with our identifiers.<br>
>We use  [*Get-Alias*](./Lecture_1/9_GetAllAliases.png) command to display all the aliases present on the current system.<br>
>*Get-Alias* is a cmdlet.
``` 
    Get-Alias
```
> The Output for the same is [here](./Lecture_1/7-dir-GetChildItem.png)<br>
> The output shows o/p of 2 commands the first one is cmdlet - *Get-ChildItem* and the second is alias - *dir*.<br>
> Another comman alias - *cd* is equivalent to *Set-Location*. [Example](./Lecture_1/8_cd-SetLocation.png)<br>

``` 
    Get-Alias < alias-name >
```
> Checks if the alias exists, if yes displays the [output](./Lecture_1/9.1_GetAliasforSpecificCommand.png)<br>
> This is a cmdlet but it gets the info about the alias
<br>

``` 
    help < alias-name >
```
> Checks if the alias exists, if yes displays the [details](./Lecture_1/10_Help-Aliases-MANPAGE.png) of the alias.<br>
> This is a cmdlet but it gets the info about the alias
<br>

``` 
    new-alias -name < alias-name > -value < corresponding-cmdlet >
```
> The above command is used in creating your own alias as per your needs. [Example](./Lecture_1/11_creating_aliases.png) of the alias.<br>
> This is a cmdlet but it is used to create the alias
<br>

``` 
    Remove-Item Alias:< alias-name >
```
> The above command is used in removing an alias. [Example](./Lecture_1/12_RemoveAliases.png).<br>
> This is a cmdlet but it is used to delete the alias
<br>


set execution policies
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```


Get Execution Policy
```
Get-ExecutionPolicy
```


```
$fName =$args[0]
$lName = $args[1]
write-Host "Hello Butch"
Write-Warning "$fName $lName"
```

```
write-host "First write"
write-host "This is your computer logged in from $env:COMPUTERNAME"
write-host "Mogambokhush hua"
Get-ExecutionPolicy
```

To get a full name or to get the full output we 
can use
```
Get-Service | Format-Table -Wrap
```

If in place of table we want the same thing as 
list, then
```
Get-Service | Format-List
```

```
$varname = get-service -name Bits | select name, status
write-host $varname
```


Get-Service | select -property name,starttype

(get-service|?{ $_.Status -eq "Stopped" -and $_.StartType -eq "Automatic"})|
select DisplayName, StartType, Status

Get-Service | Select-Object -Property Name,Status,StartType | where-object {$_.Name -eq "MpsSvc"} | Format-Table -auto


Get-Service BITS | Select StartType
