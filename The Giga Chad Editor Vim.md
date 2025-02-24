# The Giga Chad Editor Vim

## Resources to learn vim

- `vimtutor`
- vim adventures
- :`h usr`

## Vim Terminologies

- Buffer is the representation of the file in the memory which we are working on.
- Window is the representation of the buffer
- Tab is like a new viewport
- A split is splitting a window

## Basic Navigation

```python
# for movement
h, j, k, l (left, down, up, right)
# recenter the screen
zz
# exit
:q
# exit and save
:wq
# exit and don't save
:q!
# exit instantly
ZZ
# hop the content by word
w (to hop forward)
b (to hop backward)
# go to top
gg
# go to bottom
Shift + g
```

## Editing

```python
# Deleting
dd or Shift+D
# undo
u
# yank
yy
# paste
p (paste below), Shift+p (paste above)
# enter visual mode
v
# visual line mode
Shift + v
# insert mode
i (left side of the cursor)
a (right side of the cursor)
Shift + i (cursor to the first non-whitespace character)
Shift + a (goes to the end of the line)
# new line
o (for making a newline while repecting the indentation of the language)
Shift + o (new line above the current line)
```

## Customizing vim view

```python
# automatically scroll when 8 lines away from the bottom
:set scrolloff=8
# setting line numbers
set number
# setting relative numbers
set relativenumber
set rnu

# Changing the color scheme
colorscheme
```

## Saving vim settings

```python
# cd /home/user/.config/nvim/init.vim
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=The+Giga+Chad+Editor+Vim.md&fileType=undefined&fileExtension=md