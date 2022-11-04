---
layout: wiki
title: Windows Terminal
cate1: Tools
cate2:
description: Create a useful Windows Terminal
keywords: Windows Terminal
---

Windows Terminal is a new console terminal created by Microsoft. It is still in Preview version, but it can be used well after some configurations.

## custom themes

You can go to <https://github.com/mbadolato/iTerm2-Color-Schemes> to find a suitable theme under windowsterminal.

## custom configuration file location

I want to put the configuration file under HOME Directory, and then manage it through git, which can be done by the following methods:

First cut ~/AppData/Local/Packages/Microsoft.WindowsTerminal_8wekyb3d8bbwe/RoamingState/profiles.json file to ~/Windows-terminal-profiles.json, then open PowerShell with administrator privileges, execute

````
New-Item -ItemType SymbolicLink -Path ~/AppData/Local/Packages/Microsoft.WindowsTerminal_8wekyb3d8bbwe/RoamingState/profiles.json -Target ~/windows-terminal-profiles.json
````

See my Windows Terminal files at <https://github.com/mzlogin/config-files/blob/master/windows-terminal-profiles.json>

## Manage PowerShell configuration via git

Open PowerShell with administrator privileges, execute

````
New-Item -ItemType SymbolicLink -Path ~/Documents/WindowsPowerShell/Microsoft.PowerShell_profile.ps1 -Target ~/powershell.ps1
````

If using PowerShell 7 Preview, execute

````
New-Item -ItemType SymbolicLink -Path <My Documents>/PowerShell/Microsoft.PowerShell_profile.ps1 -Target <personal Directory>/powershell.ps1
````

The above two directories need to use absolute paths, otherwise an error will be reported.

See <https://github.com/mzlogin/config-files/blob/master/powershell.ps1> for my PowerShell configuration

## Customize shortcut keys

For example, adding the following content to the globals -- keybindings of the json configuration file can map the copy and paste of Windows Terminal to ctrl+c and ctrl+v (I really want to complain here, why not give the default mapping?):

*Updated 2020-04-26: The following are no longer needed to be mapped manually. The new version has default mappings. *

````json
{ "command": "copy", "keys": ["ctrl+c"] },
{ "command": "paste", "keys": ["ctrl+v"] }
````

split pane and move focus within panes:

````json
{ "command" : "splitHorizontal", "keys": [ "alt+-" ] },
{ "command" : "splitVertical", "keys": [ "alt+\\" ] },
{ "command" : "closePane", "keys": [ "alt+w" ] },
{ "command" : "moveFocusLeft", "keys": [ "alt+left" ] },
{ "command" : "moveFocusRight", "keys": [ "alt+right" ] },
{ "command" : "moveFocusUp", "keys": [ "alt+up" ] },
{ "command" : "moveFocusDown", "keys": [ "alt+down" ] }
````

Reference: <https://github.com/microsoft/terminal/blob/master/doc/user-docs/UsingJsonSettings.md>