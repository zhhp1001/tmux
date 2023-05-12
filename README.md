# tmux color

https://github.com/tmux/tmux/issues/1246


Edit ~/.tmux.config
#  bit color
set -g default-terminal "tmux-256color"
set -ga terminal-overrides ",*256col*:Tc"
Edit: .vimrc

" Enable true color 24 bit
if exists('+termguicolors')
  let &t_8f = "\<Esc>[38;2;%lu;%lu;%lum"
  let &t_8b = "\<Esc>[48;2;%lu;%lu;%lum"
  set termguicolors
endif

