# Starting with Jay Ganesh

# Install tmux
0. ```sudo apt install tmux```

# Session Management
1. List all sessions:
- ```tmux ls```

2. Create a new session:
- ```tmux new-session -s sess_name```
- ```tmux -v``` or ```tmux .``` Creating new session without name

3. Attach to an existing tmux session:
- ```tmux attach -t sess_name```

4. Detach from the current session: 
- Press `Ctrl + b`, then `d` (detached from the current session)

5. Rename the current session: 
- Press `Ctrl + b`, then `$`

6. Switch between sessions: 
- Press `Ctrl + b`, then `s` to choose the session

7. Kill a session:
- ```tmux kill-session -t sess_name or tmux kill-session . ```


# Windows Management (You need to be in a session)
1. Create a new window: 
- Press `Ctrl + b`, then `c`

2. List all windows: 
- Press `Ctrl + b`, then `w`

3. Switch between windows: 
- Press `Ctrl + b`, then `n` (next window), `p` (previous window), or the window number

4. Rename the current window: 
- Press `Ctrl + b`, then `,`

5. Move the position of windows: 
- Press `Ctrl + b`, then `.` and choose the index where you want to move the window (e.g., `Ctrl + b -> . -> 2` will move the current window to index 2)

6. Exit or delete a window: 
- Type `exit` in the window, or: ```tmux kill-window -t win_num``` or ```ctrl + b, then x```


# Pane Management (You need to be in a window)
1. Create a new pane in the current window:
- Press `Ctrl + b`, then `" ` (horizontal split) or `%` (vertical split)

2. Move between panes: 
- Press `Ctrl + b`, then use the arrow keys, or press `Ctrl + b`, then `o` (next pane) and `;` (previous pane)

3. Resize a pane: 
- Press `Ctrl + b`, then hold `Ctrl` and use the arrow keys to resize the pane

4. Convert a pane into a window: 
- Press `Ctrl + b`, then `!`

5. Kill a pane: 
- Press `Ctrl + b`, then `x`

6. Toggle pane zoom (zoom in/out): 
- Press `Ctrl + b`, then `z`

7. Synchronize panes (broadcast input to all panes): 
- Press `Ctrl + b`, then type:
  ```
  :setw synchronize-panes on
  ```
To turn off synchronization:
  ```
  :setw synchronize-panes off
  ```

8. Switch layouts: 
- Press `Ctrl + b`, then `Space` (this will cycle through different layouts for your panes)

# Plugins management

1. Clone tmux-plugins tpm : ```git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm```
2. Edit .tmux.conf
```
# Tmux Plugin Manager
run-shell ~/.tmux/plugins/tpm/tpm

# Example plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-resurrect'   # Automatically saves and restores tmux sessions
set -g @plugin 'tmux-plugins/tmux-continuum'   # Continuous session saving
set -g @plugin 'jimeh/tmux-themepack'         # Provides themes for tmux
```
3. Reload tmux conf file : ```:source-file ~/.tmux.conf```
4. Install plugins : ```ctrl + b, then I```
5. Update plugins :  ```ctrl + b, then Alt + I```

# Save & Restore sessions
1. Create and open any session you like.
2. Save session : ```ctrl + b, then ctrl + s```
3. Restore session : ```ctrl + b, then ctrl + r``` this will restore session that you lost after booting your girlfriend.

