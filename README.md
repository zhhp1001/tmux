# tmux color


Edit `~/.tmux.config`
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
# Reference
1. https://github.com/tmux/tmux/issues/1246
2. https://github.com/tmux/tmux/issues/2191
