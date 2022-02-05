# Vim Cheat Sheet
>[Vim](https://www.vim.org) is a highly configurable text editor built to make creating and changing any kind of text very efficient.

| **Table of Contents** |
| -- |
[defaults](#defaults)
[how to move](#move-in-normal-and-visual-mode)
[insert mode](#insert-mode)
[visual mode](#visual-mode)
[normal mode](#normal-mode)
[using multple files](#using-multiple-files)
[tabs](#tabs)
[split windows](#split-windows)
[macros](#macros)
[other stuff](#other-stuff)
[other resources](#other-resources)

## defaults
| Commands | Explanation |
| -- | -- |
```:q``` | quit the current tab
```:q!``` | force quit the current tab
```:qa``` | quit all tabs
```i``` | get into INSERT (write) mode
```v``` | get into VISUAL mode
```:w``` | write changes to file
```ESC``` | exit any mode

## move in NORMAL and VISUAL mode
| Commands | Explanation |
| -- | -- |
```j``` | move a line up
```k``` | move a line down
```h``` | move left
```l``` | move right
```0``` | move to the end of the line
```$``` | move to the beginning of the line
```gj``` | move a visual line up (for wordwrap)
```gk``` | move a visual line down
```gg``` | move to the top of the file
```G``` | move to the bottom of the file
```3G``` | move to line 3
```3j``` \| ```3+``` | move 3 lines up from current position
```3k``` \| ```3-``` | move 3 lines down from current position
```}``` | move to next block
```{``` | move to previous block

## insert mode
| Commands | Explanation |
| -- | -- |
```i``` | get into INSERT mode in front of of the cursor
```I``` | get into INSERT mode in front of of the current line
```a``` | get into INSERT mode at the end of the cursor
```A``` | get into INSERT mode at the end of the current line
```o``` | create a new line after the current line and get into INSERT mode
```O``` | create a new line before the current line and get into INSERT mode
```c``` | replace the selected content and get into INSERT mode

## visual mode
| Commands | Explanation |
| -- | -- |
```v``` | get into VISUAL mode
```V``` | get into VISUAL line mode
```<C-v>``` | get into VISUAL block mode
```y``` | "yank" (copy) selected content to vim; ```p``` to paste in NORMAL mode
```"+y``` | to copy selected content to system clipbaord
```d``` | cut selected content to vim
```x``` | delete selected content
```>``` | indent selected lines
```<``` | de-indent selected lines
```u``` | change selected content to lowercase
```U``` | change selected content to uppercase
```I``` | insert in front of of all selected lines (only in block mode)
```A``` | insert at the end of all selected lines (only in block mode)

## normal mode
| Commands | Explanation |
| -- | -- |
```p``` | paste previously yanked content
```P``` | paste previously yanked content in front of the cursor
```]p``` | paste previously yanked content and adjust to current indention
```"+p``` | paste system clipboard content
```u``` | undo last change
```<C-r>``` | redo last change
```.``` | insert last change at current position
```r``` | replace current character
```R``` | get into REPLACE mode (replace all following characters)
```>>``` | indent current line
```<<``` | de-indent current line
        
## search
| Commands | Explanation |
| -- | -- |
```n``` | go to next search result
```N``` | go to previous search result
```/``` | search for following text, press ESC to to jump to previous position or enter to finish search
```//``` | search again for last search pattern
```*``` | search for currently selected word
```#``` | search backwords for currently selected word
```:s/abc/def/``` | replace all instances of abc with def in the current line or selected lines (uses RegEx)
```:%s/abc/def/g``` | replace all instances of abc with def in the current file
```:noh``` | remove highlighting of search results

## using multiple files
| Commands | Explanation |
| -- | -- |
```:e``` | open/create a new a file
```:bad``` | add file to buffer without loading it
```:ls``` | list current buffers
```:bn``` | go to next buffer
```:bp``` | got to previous buffer
```:3b``` | got to 3rd buffer
```:bd``` | close buffer
```:3bd``` | close buffer 3

## tabs
| Commands | Explanation |
| -- | -- |
```:tabnew``` | create new tab/ open file in new tab
```gt``` | move to next tab
```gT``` | move to previous tab
```3gt``` | move to 3rd tab

## split windows
| Commands | Explanation |
| -- | -- |
```<C-ws>``` \| ```:sp``` | split window horizontally
```<C-wv>``` \| ```:vs``` | split window vertically
```<C-ww>``` | switch windows
```<C-wj>``` | switch to the window below
```<C-wk>``` | switch to the window above
```<C-wh>``` | switch to the window on the left
```<C-wl>``` | switch to the window on the right
```<C-wx>``` | change current window with another one

## macros
| Commands | Explanation |
| -- | -- |
```qa``` | start recording macro a
```q``` | stop recording
```@a``` | run macro a

## other stuff
| Commands | Explanation |
| -- | -- |
```:ter``` | start a terminal session

## other resources
| Source | About |
| -- | -- |
vimtutor | vim learning utility shipped with vim
[rtoor](https://vim.rtorr.com) | Vim Cheat Sheet
