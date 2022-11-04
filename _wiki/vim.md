---
layout: wiki
title: Vim
cate1: Tools
cate2: Editor
description: Personal most commonly used Vim operations.
keywords: Vim
---

### move

** in word (character) unit**

| Function | Button |
|:-----|:-----|
| on | `k` |
| down | `j` |
| Left | `h` |
| right | `l` |

**In words**

| Function | Button |
|:--------------------------------------|:-----|
| previous word ending | `ge` |
| next word start | `w` |
| Beginning of this word (if already at the beginning of this word, skip to the beginning of the previous word) | `b` |
| At the end of this word (if it is at the end of this word, skip to the end of the next word) | `e` |

**in units of screen**
 
| Function | Button |
|:---------------|:---------|
| Page down | `CTRL-f` |
| Page up | `CTRL-b` |
| Half page down | `CTRL-d` |
| Half page up | `CTRL-u` |
| Go up one line | `CTRL-y` |
| Next line | `CTRL-e` |
| Cursor moves to the top of the screen | `H` |
| Move cursor to middle of screen | `M` |
| Cursor moves to the bottom of the screen | `L` |
| Move the cursor to the top of the screen | `zt` |
| Move the cursor to the middle of the screen | `zz` |
| The cursor position moves to the bottom of the screen | `zb` |

**Line number**

| Function | Button |
|:------------|:----------------------------|
| skip to line num | `:num` or `numG` or `numgg` |

**document**

| Function | Button |
|:------------|:-----|
| skip to file header | `gg` |
| Skip to end of file | `G` |

### edit

#### copy

| Function | Button |
|:-----------------|:------|
| Copy the word under the cursor | `yiw` |
| Copy the line where the cursor is | `yy` |

#### paste

| Function | Button |
|:---------------|:-----|
| Paste after cursor | `p` |
| Paste before cursor | `P` |

#### cut

| Function | Button |
|:---------------|:-----|
| Cut selection | `d` |
| Cut the line where the cursor is located | `dd` |

#### replace

| Function | Button |
|:--------------------------------|:------------ --------|
| Replace str1 with str2 in full text | `:%s/str1/str2/g` |
| Replace str1 with str2 in lines 1 to 5 | `:1,5s/str1/str2/g` |

#### upper and lower case

| Function | Button |
|:--------------------|:----------------|
| Swap the case of the selected content | `~` |
| Convert the selection to lowercase | `gu` |
| Convert the selection to uppercase | `gU` |
| lowercase the current line | `guu` |
| Uppercase the current line | `gUU` |
| Replace matches with uppercase | `:%s/xxx/\U&/g` |
| Replace matches with lowercase | `:%s/xxx/\L&/g` |

Note: `&` represents all regular expression matches, and `\1`, '\2', ..., `\9` represent the 1st to 9th matches.

### choose

| Function | Button |
|:--------------------|:--------------------|
| Select the last selected area | `gv` |
| Select bracketed area | `vi{`, `vi[`, `vi(` |

### search

| Function | Button |
|:--------------------|:-------|
| Find string down | `/str` |
| Look up string | `?str` |
| find next | `n` |
| Find previous | `N` |
| Go down to the word under the cursor | `*` |
| Go down to the word under the cursor | `#` |

### Regular expressions

| Function | Button |
|:---------------|:--------------------------------|
| Match left word boundary | `\<` |
| Match word right boundary | `\>` |
| Deduplication | `:g/^\(.*\)$\n\1/d` |

### Commonly used

| Function | Button |
|:-------------------------|:-------------|
| delete blank lines | `:g/^$/d` |
| undo/UNDO | `u` |
| redo/REDO | `C-r` |
| Count lines/words/characters/bytes | `g C-g` |
| Remove UTF-8 BOM | `:set nobomb` |
| Keep UTF-8 BOM | `:set bomb` |

### Global

| Function | Button |
|:------------|:-----|
| quit | `:q` |
| Enforce | `!` |
| Execute external commands | `:!` |

### file operations

| Function | Button |
|:-------------------|:----------|
| open | `:e` |
| Open file dialog | `:bro e` |
| save | `:w` |
| Save As Dialog | `:brow` |
| View history file list | `:ol` |
| View and open history files | `:bro ol` |
|Rename current file|`:f filename`|

### vimdiff

| Function | Button |
|:-------------|:-------------|
| Move to previous difference | `[c` |
| move to next difference | `]c` |
| This diff uses the current file's | `dp` |
| This diff uses the | `do` | of the other file
| Manual refresh re-diff | `:diffupdate` |

### Buffer

| Function | Button |
|:-----------------------------------|:---------|
| View Buffer List | `:ls` |
| Go to the next Buffer in the Buffer list | `:bn` |
| Go to the previous Buffer in the Buffer list | `:bp` |
| Go to Buffer number num in the Buffer list | `:bnum` |
| A Buffer you were in before | `:b#` |
| Remove Buffer number num from the Buffer list | `:bdnum` |

### Combining commands

Commands can be combined using `|`, such as `cmd1 | cmd2`.

### code

| Function | Button |
|:-------------------------|:---------------------- ---------|
| Format code | `gg=G` |
| Remove line numbers at the beginning of lines 1-20 | `:1,20s/^\\s\*[0-9]\*\\s\*//g` |
| Expand Collapse All | `zR` |
| Expand current level fold | `zr` |
| Collapse all | `zM` |
| current level collapse | `zm` |
| Toggle collapse/expand | `za` |
| Recursively collapse/expand the current large block | `zA` |
| Collapse current block | `zc` |
| Recursively fold the current large block | `zC` |
| Expand current block | `zo` |
| Recursively expand the current large block | `zO` |
| format json data | `:%!python -m json.tool` |
| Indent current line | `>>` |
| Unindent current line | `<<` |

### modeline

Writing:

````
 vim: set ft=markdown:
 vim: ft=markdown

// vim: noai:ts=4:sw=4
/* vim: noai:ts=4:sw=4 */
````

### Plugins

####CtrlP

Basic keys `C-p`

| Function | Button |
|:-----------------------------------|:----------|
| Refresh list | `F5` |
| switch file/buffer/MRU | `C-f/b` |
| Toggle full path search/filename search | `C-d` |
| Toggle regular expression mode | `C-r` |
| Previous/next options | `C-k/j` |
| Open file in new tab/vertical split/horizontal split | `C-t/v/x` |
| Select the previous/next record in history | `C-p/n` |
| Create a file and its parent path | `C-y` |
| Mark and open multiple files | `C-z C-o` |
| Exit CtrlP | `C-c` |

#### LeaderF

| Function | Button |
|:-----------------------------------|:------------ ------------|
| Open file | `Leader-f` |
| open buffer | `Leader-b` |
| Open MRU | `Leader-m` (custom) |
| exit | `C-c` |
| Toggle between fuzzy search and regular search | `C-r` |
| Paste | `C-v` |
| Clear input | `C-u` |
| Previous/next options | `C-k/j` |
| Open file in new tab/vertical split/horizontal split | `C-t/]/v` |
| Refresh list | `F5` |

#### vim-table-mode

| Function | Button |
|:---------------|:-------------|
| Delete column | `Leader-tdc` |
| delete line | `Leader-tdd` |
| Reformatting table | `Leader-tr` |

#### markdown-preview.nvim

| Function | Button |
|----------|------|
| Preview | `F5` |
| Stop preview | `F6` |

Export PDF: After previewing, use the "Print" function of the browser, select "Save as PDF" for the printer, cancel "Header and Footer", and then click Save.

### Command Line

Jump to a specified line when opening Vim:

````
vim +[num] filename
````

num indicates the line number, if not filled, it will jump to the end of the file.