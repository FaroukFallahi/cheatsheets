# Tmux
Oh dear tmux, how would we even survive in a server without you :)

## Basics
- `Ctrl+b` `?`: list commands (help)
- `Ctrl+b` `d`: detach session (i like to call it daemonize)
- `$ tmux ls`: lists your tmux sessions (like the daemonized one above)
- `$ tmux attach-session -t <num>`: attachs the target session <num> (brings to foreground) 

## Handling windows
- `Ctrl+b` `c`: create a new window
- `Ctrl+b` `w`: choose window from a list
- `Ctrl+b` `0`: switch to window 0
- `Ctrl+b` `,`: rename the current window

## Handling panes
- `Ctrl+b` `%`: split current pane horizontally
- `Ctrl+b` `"`: split current pane vertically
- `Ctrl+b` `o`: go to the next pane
- `Ctrl+b` `;`: toggle between the current and previous pane
- `Ctrl+b` `x`: close the current pane (but i rather `Ctrl+d` to kill the shell)
- `Ctrl+b` `any arrow key`: goes in the desired direction (immediate follow-up directions are also possible)
