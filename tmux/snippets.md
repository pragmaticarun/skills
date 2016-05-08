#Create tmux session

```bash
tmux
tmux new-session -s <session name>
tmux new -s <session name>
tmux new -s <session name> -d 
```

#Exiting tmux sessions

```bash
exit
```

#Detaching from a session

```
PREFIX CTRL + b
PREFIX d
```

#Listing active sessions

```
tmux list-sessions
tmux ls
```

#Attaching to a session

```
tmux attach
tmux attach -t second_session
```

#Killing a tmux session

```
tmux kill-session -t basic
tmux kill-session -t second_session
```

#Creating a named window

```
tmux new -s windows -n shell
```

#Adding a window to a session

```
PREFIX c
```

#Renaming a window

```
PREFIX ,
```

#Moving between windows

```
PREFIX n
PREFIX p
PREFIX <window number>
PREFIX w # List of windows
PREFIX f # search by window name
```

#Closing a window

```
PREFIX &
```

#Creating Panes

## Splitting a window horizontally

```
PREFIX "
```

## Splitting a window Vertically

```
PREFIX %
```

#Moving between Panes

```
PREFIX o  # Cycle through panes
PREFIX <navigation keys>
```

#Layout of the Panes

```
even-horizontal
even-vertical
main-horizontal
main-vertical
tiled

PREFIX SPACE
```

#Closing a Pane

```
PREFIX x
```


#Entering command mode

```
PREFIX :
```
