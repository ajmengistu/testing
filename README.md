```
# Open new window frame via (ctrl + a + v or ctrl + a + h) horizontal or vertical in the SAME working directory.

# Disable pane switching with Esc (when switching to Normal mode in Vim &  hit j or k)
set -s escape-time 0
# Send prefix (Below three lines set prefix to Ctrl-A)
set-option -g prefix C-a
unbind-key C-a
bind-key C-a send-prefix

# Use Alt-arrow keys to switch panes (Alt+h to move left)
bind -n M-h select-pane -L
bind -n M-l select-pane -R
bind -n M-k select-pane -U
bind -n M-j select-pane -D

# Shift arrow to switch windows
bind -n S-Left previous-window
bind -n S-Right next-window

# Mouse mode
setw -g mouse on

# Set easier window split keys
bind-key v split-window -h
bind-key h split-window -v

# Easy config reload
bind-key r source-file ~/.tmux.conf \; display-message "~/.tmux.conf reloaded."

# vim keys for copying and pasting
set-window-option -g mode-keys vi

# Automatically update current opened file on vim, when there has been writes to it.
# see: https://vi.stackexchange.com/questions/444/how-do-i-reload-the-current-file
set -g focus-events on

# ----------------Copy & Paste using Vim----------------------
# https://stackoverflow.com/questions/61034568/tmux-config-what-is-t-in-bind-key-setting-should-mean 
# https://github.com/gotbletu/shownotes/blob/master/tmux_copy_mode_vim.txt
# Source: https://wiki.archlinux.org/index.php/Tmux#X_clipboard_integration
# Original source (above) was published in 2013. Thus, the -t flag has been dropped use `send -X` and `copy-mode-vi`. 

bind-key Escape copy-mode				# enter copy mode; default [
bind-key -Tcopy-mode-vi Escape send -X cancel 
bind-key -Tcopy-mode-vi v send -X begin-selection 	# begin visual mode
bind-key -Tcopy-mode-vi V send -X select-line 		# visual line
bind-key -Tcopy-mode-vi r send -X rectangle-toggle  	# visual block toggle

bind-key -T copy-mode-vi y send-keys -X copy-pipe-and-cancel "xclip -i -sel clip > /dev/null" 	# yank (copy) to system clipboard 
bind-key p run "xclip -o -sel clip | tmux load-buffer - ; tmux paste-buffer"   			# paste (p); default ]
```
