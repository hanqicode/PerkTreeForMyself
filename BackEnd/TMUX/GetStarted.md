# Get Started

## What's TMUX?
TMUX stands for **Terminal Multiplexer**. 

## Why should I learn TMUX?
Besides opening multiple windows and panes, there is a strong reason: attaching/detaching session.

For example,  
If you're running a job in terminal and it is time consuming, you cannot close the terminal. 
Otherwise, the job will be shut down.

If you have TMUX, you can detach the session and close the terminal safely. The job will run in background.
You can attach the session once you open terminal again.

This is very useful when work with remote servers like using `ssh`.

## Commands
`control + b` is a default **PREFIX** in TMUX.

### Session
1. Create a new session
```bash
tmux new -s <name>
```

2. detach the session
```bash
PREFIX + d
```

3. attach the session
```bash
tmux attach -t <name>
```

4. list all sessions
```bash
tmux ls
```

5. exit a session
```bash
exit
```
