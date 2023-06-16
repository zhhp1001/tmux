# Install
1. Follow wiki to install tmux with `version > 3.1 `
 
   https://github.com/tmux/tmux/wiki

2. git clone config file to `~/.config/tmux/tmux.conf` 

# tmux color
Edit `tmux.conf`

```bash
set -g default-terminal "tmux-256color"
set -ga terminal-overrides ",*256col*:Tc"
```
Edit: `~/.vim/vimrc`

```bash
" Enable true color 24 bit
if exists('+termguicolors')
  let &t_8f = "\<Esc>[38;2;%lu;%lu;%lum"
  let &t_8b = "\<Esc>[48;2;%lu;%lu;%lum"
  set termguicolors
endif
```
Edit: `~/.bashrc`

The `$TERM` in tmux should be equal to outside of tmux, when using Truecolor.
```bash
export TERM=xterm-256color
```
# VSCode

Add the following content to ~/.bashrc or ~/.zshrc

```bash
socket=$(ls -1t /run/user/$UID/vscode-ipc-*.sock 2> /dev/null | head -1)
export VSCODE_IPC_HOOK_CLI=${socket}
```

`source ~/.bashrc` when this connection issue occured:

```bash
Unable to connect to VS Code server: Error in request.
Error: connect ENOENT /run/user/1000/vscode-ipc-71ef2cb8-3830-4c40-8bc3-a611f677336c.sock
    at PipeConnectWrap.afterConnect [as oncomplete] (node:net:1247:16) {
  errno: -2,
  code: 'ENOENT',
  syscall: 'connect',
  address: '/run/user/1000/vscode-ipc-71ef2cb8-3830-4c40-8bc3-a611f677336c.sock'
}
```
# Cheat Sheet

## Prefix
`Ctrl + s`

## Window Management
Prefix `c` Create window
Prefix `&` kill current window

## Window Navigation
`Alt + window_number`

## Pane Management
Prefix `l` Right

Prefix `h` Left

Prefix `j` Down

Prefix `k` Up

Prefix `x` kill current pane

## Pane Navigation
`Alt + shift + window_number` Move current pane to window_number

`Alt + l` Right

`Alt + h` Left

`Alt + j` Down

`Alt + k` Up

Prefix `W` Choose tree

Prefix `V` Choose tree

Prefix `S` Choose tree

## Pane Reorg 
`Alt + f` Pane full screen

`Alt + space` Change layout

Prefix `>` Swap pane

Prefix `<` Swap pane

Prefix `|` Swap pane

`Alt + shift + H` Resize pane

`Alt + shift + J` Resize pane

`Alt + shift + K` Resize pane

`Alt + shift + L` Resize pane

### Move pane to another window
`Alt + shift + window_number` Move current pane to window_number

## Copy Mode
`Alt + v`  Enter copy mode

`q`        Exit copy mode

`space`    Hight text

`Enter`    Copy and Exit copy mode

Prefix `b` list buffers

Prefix `p` paste buffer

Prefix `-` delete the most recently copied buffer of text

Prefix `=` Choose which buffer to paste

## Session
`tmux ls`

`tmux kill-server`

`tmux kill-session -t session_number`

`tmux a -t session_number`

# Terminal Emulator
Windows: terminal

## Auto SSH
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

## Enable Right Click Paste
```
"copyOnSelect": true
```

## Unbound `Alt + Space`
```
{ "command": "unbound", "keys": "alt+space" }
```

# Reference
1. https://github.com/tmux/tmux/issues/1246
2. https://github.com/tmux/tmux/issues/2191
3. https://linuxhint.com/use-new-windows-terminal-ssh/
