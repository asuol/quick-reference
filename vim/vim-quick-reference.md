# VIM Quick Reference

By Andre Lousa Marques

## Table of contents

TBD

# Universal VIM stuff

## Navigation

- `f,` to move cursor to next comma
- `t,` to move cursor just before the next comma

## Buffering
 - :b lets you autocomplete any open buffer (`:b ser` will open the buffer for any open file that has the "ser" substring)

## open files

- `:e` to open file for edit

## Windows

- `ctrl + w + s` horizontal split
- `ctrl + w + v` vertical split
- `ctrl + w + q` close window
- `ctrl + w + o` close all windows except the current one

## Registers

- `"add` deletes line and places it into register `a`
- `"ay` yanks into register `a`
- uppercase register name appends to its value. E.g.: `"Add`
- `:reg` to show all register contents
- `"%p` to write the current file path
- `"1p` prints second last deletion (dd) valid from 1 to 9
- `+` register represents the clipboard
- `:let @+=@%` to place in the clipboard the path to current file (e.g.: for usage in another terminal)
- Use `ctrl+r /` to retrieve the last text search and fill for a substitution command, e.g.: `:s/<ctrl+r />/xxx/`
- `let @w="<ctrl+r w>"` to edit the macro stored at register w. When done close the ' quote

References: https://www.brianstorti.com/vim-registers/

## Macros

- `qw` starts recording a macro to register `w`. Hit `q` to stop recording
- `qW` (upper case register name) can be used to resume recording a macro
- use `:reg w` to see the contents of the macro. Notice that the special characters like ESC and ENTER were replaced with the Vim representation ^[ and ^M respectively.
- `@w` to replay the macro
- When manually writing/editing a macro text, note that caret symbols such as `^[` that vim uses cannot be used to set a macro value with `let @<reg>`. Use instead `\<cr>` (for `^M`), `\<esc>` (for `^[`) and `\<tab>` (for `^I`). Also use double quotes around the value in `let @<reg>="value"`. Note: the vim `^[` symbol can be written with `ctrl+v <escape key>`

References: https://www.redhat.com/sysadmin/use-vim-macros

TODO: https://www.hillelwayne.com/post/vim-macro-trickz/

## Quitting

- ZZ to save and quit, instead of :wq or :x
- ZQ to quit without saving, instead of :q!

## Help

- `:h ^n` for instance to know what `^n` does in normal mode
- `:h i_^n` for instance to know what `^n` does in insert mode
- `:h c_^n` for instance to know what `^n` does in command mode
- `:helpgrep` to grep the vim help pages

## Tag jumping

(Requires tag file) is this relevant?

 - Use ^] to jump to tag under cursor
 - Use g^] for ambiguous tags
 - Use ^t to jump back up the tag stack

## AUTOCOMPLETE

The good stuff is documented in |ins-completion|

 - ^n for anything specified by the 'complete' option
 - ^x^n for JUST this file
 - ^x^f for filenames (for autocomplete filenames, from anywhere in the system)
 - ^x^] for tags only

To navigate the autocomplete window:
 - Use ^n and ^p to go back and forth in the suggestion list
 - Use ^y to confirm and ^e to cancel

# Specific to my VIMRC

VIMC located at TBD

Place universal vim configuration at a `no_plugins.vim`, and plugin configuration at a separate file. This way I can choose to use plugins or not

## Fuzzy search

 - Hit tab to :find by partial match
 - Use * to make it fuzzy

## Plugins

### vim-plug

Installation automatic via .vimrc (see https://github.com/junegunn/vim-plug#unix)

For commands, see https://github.com/junegunn/vim-plug#commands

### YCM

#### Installation

https://github.com/ycm-core/YouCompleteMe#installation

1. Install plugin via vim-plug
2. 
```
cd ~/.vim/plugged/YouCompleteMe
python3 install.py --all
```

#### Usage

`,g` to go to reference
`,r` to rename current symbol

### vim-flake8

#### Installation

`pacman -S flake8`

#### Usage

Press `F7` to lint the current file
