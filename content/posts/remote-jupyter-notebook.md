+++
date = "2020-05-25"
draft = false
title = "Remote Jupyter notebook locally over ssh gate"
tags = ["python", "jupyter notebook", "ssh", "ssh config"]
categories = ["Software Development"]
toc = true
+++

## Problem

I have encountered several times this problem:

> Me: *I want a nice interface to run python code in a remote machine.*

> Jupyter Notebook: *I am here for you.*
	
> SSH Gate: *I'll make things trickier.*

Well, here is the guide to setup a jupyter notebook server in a remote machine and connect to it, even if you need to pass through an ssh gate.

This guide is for UNIX-like systems and has been tested on Ubuntu 18.04.

## Solution

Create an ssh config to login to your remote server in file `.ssh/config`

```
Host <host-machine>
  Hostname <remote hostname> #something like remotehost.com
  ProxyCommand ssh <gate-name>  -W %h:%p 
  User <username>
  LocalForward 18888 localhost:8888

Host <gate-machine>
  Hostname <sshgate hostname> 
  User <username>
```

You might need to set the configuration differently, depending on the settings of the server you want to connect to. This configuration basically tells the system:

> To ssh into `host-machine`, you first need to ssh into `gate-machine`.

> Also, expose port $8888$ of the `host-machine` to my machine on port $18888$.

## Jupyter set up

1. Having set up the configuration, connection to the remote machine is as easy as running the following command

`ssh <host-name> # as set in the config`

2. To let it continue running, when you logout create a `tmux` session (Follow a [tmux introduction](https://www.google.com/search?q=tmux+introduction) for details. If you don't know what tmux is and use the terminal, I am sure you will love it):

```tmux new -s jupyter```

You could also set it as a daemon, but I find the tmux method more versatile.
	

3. Create a python virtual environment to install the jupyter server and all the libraries you need (See my [virtual environments](/posts/python-virtualenv) post for details).

```mkvirtualenv myenv```

4. Install jupyter notebook/lab

```pip install notebook```

or

`pip install jupyter-lab`

5. Run jupyter notebook/lab server

```jupyter notebook --port 8888 #for jupyter notebook```

or

`jupyter lab --port 8888 #for jupyter lab`

and copy the token shown on the terminal screen.


6. Detach from the tmux session with `CTRL+b, d`

7. Open a browser on your local machine and go to [localhost:18888](localhost:18888) as we set up the `.ssh/config`. Use the token and enjoy running notebooks in your personal version of Google Collab.

Feel free to leave a comment if you encounter any issues.





