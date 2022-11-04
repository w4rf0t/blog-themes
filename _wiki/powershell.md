---
layout: wiki
title: PowerShell
cate1: Tools
cate2:
description: Use PowerShell to create a handy terminal under Windows.
keywords: Windows, PowerShell
---

Use PowerShell to create a handy terminal under Windows.

## Working with Cmder

It is best to take it with Cmder.

## Configuration file location

PowerShell 6 default profile `~/Documents/WindowsPowerShell/Microsoft.PowerShell_profile.ps1`.

PowerShell 7 default profile `<My Documents>/PowerShell/Microsoft.PowerShell_profile.ps1`

Cmder's PowerShell profile `<cmd_install_path>/config/user-profile.ps1`.

## alias

### Quick access to a Directory

Example: Quick access to `d:\sources\` Directory via `src` command.

```powershell
function Enter-Sources {
    cd d:\sources\
}

Set-Alias ​​src Enter-Sources
````

### Quickly open current folder

Example: Use the `e.` command to quickly open the current folder in the explorer.

```powershell
function Open-Current-Directory {
    explorer.
}

Set-Alias ​​e. Open-Current-Directory
````

### git related commands

```powershell
## gs=git status
function Git-Status {
    git status
}

Set-Alias ​​gs Git-Status

## ga=git add .
function Git-Add-All {
    git add .
}

Set-Alias ​​ga Git-Add-All

##gg=gitk
function Git-Gui {
    gitk
}

Set-Alias ​​gg Git-Gui

## gpull=git pull origin <current branch>
function Git-Pull-Current-Branch {
    $currentBranch = git symbolic-ref --short -q HEAD
    git pull origin $currentBranch
}

Set-Alias ​​gpull Git-Pull-Current-Branch

## gpush=git push origin <current branch>
function Git-Push-Current-Branch {
    $currentBranch = git symbolic-ref --short -q HEAD
    git push origin $currentBranch
}

Set-Alias ​​gpush Git-Push-Current-Branch

## g1=add, commit, push one-stop
function Git-Commit-And-Push {
    git add .
    git commit -m $args[0]
    Git-Push-Current-Branch
}

Set-Alias ​​g1 Git-Commit-And-Push
````

### objdump

```powershell
function Obj-Dump {
    D:\Android\sdk\ndk-bundle\toolchains\x86_64-4.9\prebuilt\windows-x86_64\bin\x86_64-linux-android-objdump.exe $args
}

Set-Alias ​​objdump Obj-Dump
````

## Shortcut keymap

After switching from Linux/macOS bash or even Windows cmd, I found that shortcut keys such as ctrl-u and ctrl-k are not available. PSReadLine saves you.

```powershell
# ctrl-k, ctrl-u, ctrl-a, ctrl-e, ctrl-b, ctrl-f, etc
Import-Module PSReadLine
Set-PSReadLineOption -EditMode Emacs
````

## Common commands

### View PATH environment variable

````
type env:path
````

Or display them on one line each:

````
(type env:path) -split ';'
````

You can also filter:

````
(type env:path) -split ';' | sls bin
````

## refer to

- [Quick Examine PATH Environment Variables with PowerShell](http://blog.vichamp.com/2014/08/05/quick-examine-path-env-variable-with-powershell/)