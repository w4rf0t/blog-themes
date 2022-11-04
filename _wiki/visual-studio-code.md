---
layout: wiki
title: Visual Studio Code
cate1: Tools
cate2: Editor
description: Shortcuts and tips for Visual Studio Code
keywords: Visual Studio Code
---

## hot key

C --> Ctrl

S --> Shift

M --> Alt

Cmd --> Command

| Features | Windows | Mac OS X |
|:-------------------|:------------|:---------|
| Open file | C-o | |
| Open Folder | C-k C-o | |
| close folder | C-k f | |
| Command Palette | C-S-p | |
| Explorer | C-S-e | |
| Search | C-S-f | |
| Git | C-S-g | |
| Debug | C-S-d | |
| Plugins | C-S-x | |
| Markdown side preview | C-k v | |
| Markdown Preview | C-S-v | |

## Using VSCode as mergetool

Edit the ~/.gitconfig file and add the following:

````
[merge]
    tool = vscode
[mergetool "vscode"]
    cmd = code --wait $MERGED
````

Execute git mergetool when needed and it will be called up.

Reference: <https://blog.kulman.sk/using-vscode-as-git-merge-tool/>

## Use VSCode as git commit message editor

````
git config --global core.editor "code -w"
````

## VSCodeVim supports key repeat

On macOS, the VSCodeVim mode does not support key repetition by default. For example, if you press and hold `L` in Normal mode, the cursor only moves to the right once, instead of moving all the time as you expected.

The method of enabling key repeat is described in the REAME of the plugin, link: <https://github.com/VSCodeVim/Vim#mac>

method:

Execute one of the following lines as needed and restart VSCode.

````sh
$ defaults write com.microsoft.VSCode ApplePressAndHoldEnabled -bool false # For VS Code
$ defaults write com.microsoft.VSCodeInsiders ApplePressAndHoldEnabled -bool false # For VS Code Insider
$ defaults write com.visualstudio.code.oss ApplePressAndHoldEnabled -bool false # For VS Codium
$ defaults delete -g ApplePressAndHoldEnabled # If necessary, reset global default
````

If necessary, adjust "Key Repeat" and "Delay before Repeat" in System Preferences - Keyboard.