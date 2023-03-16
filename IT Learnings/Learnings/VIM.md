---
type: learning
last-modified-date: 16-03-2023
creation-date: 16-03-2023
parent-topic: Text Editor
tags: VI Improved
---
## VIM - VI Improved
Terminal based Text editor available for UNIX based systems

## Installation Command
```bash
apt install vim-nox
```

## Verification Command
```bash
apt show vim-nox
```

## Available Modes
- Command Mode
- Visual Mode
- Insert Mode

## Navigation
Up, Down, Left, Right
H -> Left
J -> Down
K ->Up
L ->Right
gg -> Top of file
G -> End of file
A -> place cursor at the end of line
0 -> Beginning of line
$ -> End of line

## Commands
: -> To enter commands
w -> Write
q -> Quit
! -> Discard changes
u -> Undo
dd -> Delete line and copy
x -> Delete character
r -> Read file and paste content to the cursor location
bn -> buffer next
bp -> buffer previous
badd -> buffer add
e -> open file as buffer
y -> yank
p -> paste 
(visual mode)sort ui
%s/`<old>`/`<new>`/g -> replace old with new in all occurrance
split `<file-name>` -> split horizontal
^ww -> toggle between split files
vsplit / vs -> split vertical
set number -> Set line numbers on the go
set nonumber -> Remove line numbers on the go
.vimrc -> Configure vim for a folder
