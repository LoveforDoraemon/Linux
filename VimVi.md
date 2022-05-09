# Vim/Vi

[TOC]



## normal mode

* when you open a file with vim
* delete,copy,paste are available

### cursor movement

| Key       | Function                                                |
| --------- | ------------------------------------------------------- |
| C+b/C+f   | page backward/forward                                   |
| n\<space> | cursor moves right for n chars long                     |
| G/gg/nG   | cursor moves to the last/fist line of the file          |
| H/M/L     | cursor moves to the fist/middle/last line of the screen |

### find and replace

| Key                  | Function                                                     |
| -------------------- | ------------------------------------------------------------ |
| /word                | find a word str down cursor                                  |
| ?word                | find a word str up cursor                                    |
| n                    | repeat last action of findiing                               |
| N                    | repeat reverse last action of finding                        |
| :n1,n2s/str1/str2/g  | find between n1,n2 to substitue s1 with s2                   |
| :n1,n2s/str1/str2/gc | find between n1,n2 to substitue s1 with s2 and ask before substituting |

### del,cp and paste

| Key  | Function                                        |
| ---- | ----------------------------------------------- |
| nx   | =`del` delete n char bakward                    |
| nX   | =`backspace` delete N char forward              |
| ndd  | delete the downward n lines of the cursor       |
| d1G  | delete lines from line 1 to the cursor line     |
| dG   | delete lines from cursor line to the last line  |
| d$   | delete chars from cursor to the end of line     |
| d0   | delete chars from cursor to line beginning      |
| nyy  | copy the nlines downward cursor line            |
| y1G  | copy lins from cursor to the last line          |
| yG   | copy line from cursor to the first line         |
| y$   | copy chars from cursor to the end of line       |
| y0   | copy chars from cursor to the beginning of line |
| p    | paste on the next line under the cursor         |
| P    | paste on the previous line above the cursor     |
| u    | restore previous operation                      |
| C+r  | redo previous operation                         |
| .    | repeat previous operation                       |

## edit mode

* with 'Insert' in the lowed left corner
* type [a/A,i/A,s/S,o/O] to enter edit mode
* A: begin at the end of the line
* S: delete current line and begin entering
* type `esc` to quit and enter normal mode

## cmd mode

* type[:,?] to enter cmd mode

| Key               | Function                                                     |
| ----------------- | ------------------------------------------------------------ |
| :w                | save                                                         |
| :w!               | force write if authorized                                    |
| :q                | quit vim                                                     |
| :q!               | quit without saving                                          |
| :wq               | save and quit                                                |
| :x                | save and quit                                                |
| :ZZ               | save and quit                                                |
| :w filename       | save as another file                                         |
| :r filename       | read data from another file on the next line                 |
| :n1,n2 w filename | save data from n1 to n2 as another file                      |
| :! command        | temporarily leave VI to the display result of executing command in command line mode |
| :set nu           | display line nums                                            |
| :set nonu         | reverse to set nu                                            |



## visual mode

* type [v,V] to enter visual mode

## Block Selection

| Key  | Function                    |
| ---- | --------------------------- |
| v    | select the cursor char      |
| V    | select the cursor line      |
| C+v  | select in a rectangular way |

## Multi Files Editing

| Key                | Function                    |
| ------------------ | --------------------------- |
| :sp filenaem       | open a new window to        |
| vim file1 file2 .. | open multi files            |
| :n                 | edit next file              |
| :N                 | edit last file              |
| :files             | list all opened files       |
| C+w j              | cursor moves to next window |
| C+w k              | cursor moves to last window |
| C+w q              | quit                        |

## Environment Variable Settings

create a file name ~/.vimrc and write as listed below

* :set nu
* :set nonu
* :set hlsearch
* :set no hlsearcj
* :set backup
* :set ruler
* :syntax on/off
* :set bg=dark/light
