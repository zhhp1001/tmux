# tmux color

https://unix.stackexchange.com/questions/118806/tmux-term-and-256-colours-support


~/.tmux.config
```
set -g default-terminal "xterm-256color"
```

If this not works for vim in tmux, then `tmux -2` will work.
Add alias tmux='tmux -2' in ~/.bashrc.

# Reference
https://unix.stackexchange.com/questions/118806/tmux-term-and-256-colours-support
