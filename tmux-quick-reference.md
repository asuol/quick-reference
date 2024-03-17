# TMUX Quick Reference

By Andre Lousa Marques

## Table of contents

TBD

## Reloading configuration

Ensure that no TMUX instance is running (e.g.: run `tmux kill-server`). TMUX will not source the configuration file if there are active sessions.

## TMUX sessions

create named session: `tmux new -s <session_name>`
detach from session: `<prefix> d` or just close the terminal window
select session to detach: `<prefix> D`
list running sessions: `tmux ls`
switch between running sessions: `<prefix> s`
attach to session: `tmux a -t <session name>`
attach to last detached session: `tmux a`


## TMUX session windows

create new window: `<prefix> c`
move to next window: `<prefix> n`
move to previous window: `<prefix> p`
move to window 0: `<prefix> 0`

set window name: `<prefix> ,`

close window: `CTRL + D` or type `exit`

## TMUX help

`<prefix> ?`
