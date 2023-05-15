# Install
`~/.config/tmux/.tmux.config` 
# tmux color
Edit `.tmux.config`
```bash
set -g default-terminal "tmux-256color"
set -ga terminal-overrides ",*256col*:Tc"
```
Edit: ~/.vim/vimrc
```bash
" Enable true color 24 bit
if exists('+termguicolors')
  let &t_8f = "\<Esc>[38;2;%lu;%lu;%lum"
  let &t_8b = "\<Esc>[48;2;%lu;%lu;%lum"
  set termguicolors
endif
```
Edit: ~/.bashrc
The `$TERM` in tmux should be equal to outside of tmux, when using Truecolor.
```bash
export TERM=xterm-256color
```

# Cheat Sheet
## Prefix
`Ctrl + s`
## Window Navigation
`Alt + window_number`
## Create Pane
Prefix `l` Right

Prefix `h` Left

Prefix `j` Down

Prefix `k` Up
## Pane Navigation
`Alt + shift + window_number` Move current pane to window_number

`Alt + l` Right

`Alt + h` Left

`Alt + j` Down

`Alt + k` Up
## Reorg 
`Alt + f` Pane full screen

`Alt + space` Change layout

Prefix `>` Swap pane

Prefix `<` Swap pane

Prefix `|` Swap pane

## Copy Mode
`Alt + v`  Enter copy mode

`q`        Exit copy mode

# Terminal Emulator
Windows: terminal

1. Add SSH to Windows Terminal
The JSON file will open and appear on the screen. Go to the “Profiles” options menu and then move to the “list” array:

2. Paste the below-provided code in the list array after the “},” comma. Change the “commandline” information and paste your ssh credentials. Also, choose the name for your new SSH connection window.

```
       {
        "commandline": "ssh anuma@192.168.0.106",
        "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6121}",
        "hidden": false,
        "name": "Openssh"
        },
```

3. Click Openssh in the New Tab of Windows Terminal

# Reference
1. https://github.com/tmux/tmux/issues/1246
2. https://github.com/tmux/tmux/issues/2191
3. https://linuxhint.com/use-new-windows-terminal-ssh/
