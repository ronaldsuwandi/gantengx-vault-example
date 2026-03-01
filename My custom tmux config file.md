[[tmux]] config updated for 3.5a

```
###########
# general #
###########
# Replace C-b prefix with Alt+Space (so it won't clash with vim)

unbind C-b
set-option -g prefix M-Space
set-window-option -g mode-keys vi

# set-option -g default-shell /usr/local/bin/fish
# to prevent ssh from renaming window name
set-option -g allow-rename off

# enable mouse
setw -g mouse on

# Fix OSX pasteboard issue and also launching app in OSX issue (no longer needed for tmux 2.6+)
# https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
# set-option -g default-command "reattach-to-user-namespace -l fish"

# address vim mode switching delay (http://superuser.com/a/252717/65504)
set -s escape-time 0

# increase scrollback buffer size
set -g history-limit 100000

# tmux messages are displayed for 2 seconds
set -g display-time 2000

# refresh 'status-left' and 'status-right' more often
set -g status-interval 5

# focus events enabled for terminals that support them
set -g focus-events on

# super useful when using "grouped sessions" and multi-monitor setup
setw -g aggressive-resize on

# start window numbering at 1
set -g base-index 1

set -g extended-keys on

# Set parent terminal title to reflect current window in tmux session
set -g set-titles on
set -g set-titles-string "#I:#W [#P:#{pane_current_command}]"

# automatically renumber windows
set -g renumber-windows on

#############
# shortcuts #
#############
# clear screen and scroll history by simply pressing Ctrl+K
# -n allows it to run without needing of prefix key
bind -n C-k send-keys -R \; send-keys C-l \; clear-history

# Custom keys to change pane without using prefix
bind -n S-Left select-pane -L
bind -n S-Right select-pane -R
bind -n S-Up select-pane -U
bind -n S-Down select-pane -D

# Custom keys for mark/swap without using prefix
bind -n M-m select-pane -m
# Swap and clear marked pane
bind -n M-s swap-pane \; select-pane -M
bind -n S-M-Up swap-pane -U
bind -n S-M-Down swap-pane -D
bind -n M-. rotate-window -D

# NOTE - S-M-<arrow> DOES NOT WORK on tmux 3.2, FIXED on 3.5a
# bind -n S-M-Left select-pane -L
# bind -n S-M-Right select-pane -R
# bind -n S-M-Up select-pane -U
# bind -n S-M-Down select-pane -D

# Remap pane/window splitting to use current pane path
bind % split-window -h -c "#{pane_current_path}"
bind '"' split-window -c "#{pane_current_path}"
bind c new-window -c "#{pane_current_path}"

# Additional sane pane splitting shortcut
bind | split-window -h -c "#{pane_current_path}"
bind - split-window -c "#{pane_current_path}"

# M-Enter to zoom pane
bind -n M-Enter resize-pane -Z

# source .tmux.conf as suggested in `man tmux` - reload source by prefix+R or Ctrl+Alt+R
bind r source-file ~/.tmux.conf \; display ​" Reloaded tmux.conf"
bind -n C-M-r source-file ~/.tmux.conf \; display ​" Reloaded tmux.conf"

# bind prefix+0 to select last window instead of window 0
bind 0 select-window -t:$

# bind M-(number) to select window without having to use prefix
# also bind M-0 to select last window
bind -n M-1 select-window -t 1
bind -n M-2 select-window -t 2
bind -n M-3 select-window -t 3
bind -n M-4 select-window -t 4
bind -n M-5 select-window -t 5
bind -n M-6 select-window -t 6
bind -n M-7 select-window -t 7
bind -n M-8 select-window -t 8
bind -n M-9 select-window -t 9
bind -n M-0 select-window -t:$

# Capture pane content and store it into `/tmux.log
bind-key S capture-pane -b temp-capture-buffer -S - \; save-buffer -b temp-capture-buffer ~/tmux.log \; delete-buffer -b temp-capture-buffer \; display ​" Pane content stored at ~/tmux.log"

######
# ui #
######
set -g default-terminal "screen-256color"

# modes
setw -g clock-mode-colour colour5
setw -g mode-style 'fg=colour1 bg=colour18 bold'

# panes
set -g pane-border-style 'fg=colour244 bg=colour235'
set -g pane-active-border-style 'fg=colour77 bg=colour235'
set -g pane-border-format ' [#P] <#{pane_current_command}> @ #{pane_current_path} #{?window_zoomed_flag,#[fg=colour228]Z#[fg=colour77] ,}'
set -g pane-border-status 'top'

# statusbar
set -g status-style 'bg=colour234 fg=colour250'
set -g status-left '#[fg=colour228,bg=colour234] #S ' # sesion name
set -g status-right '#[fg=colour250,bg=colour236] %d %b %H:%M ' # date/clock
set -g status-right-length 50
set -g status-left-length 50

setw -g window-status-current-style 'fg=colour1 bg=colour28 bold'
setw -g window-status-current-format ' #I#[fg=colour249]:#[fg=colour255]#W#[fg=colour250]#F '

setw -g window-status-style 'fg=colour9 bg=colour236'
setw -g window-status-format ' #I#[fg=colour237]:#[fg=colour250]#W#[fg=colour244]#F '
setw -g window-status-bell-style 'fg=colour255 bg=colour1 bold'
setw -g window-status-separator ''

# messages
set -g message-style 'fg=colour237 bg=colour3 bold'
```
