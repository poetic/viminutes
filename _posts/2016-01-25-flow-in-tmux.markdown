---
layout: post
title:  "Flow in Tmux"
date:   2016-01-17 10:30:01
---
## Recap [speak in vim](http://poetic.github.io/viminutes/2016/01/17/speak-in-vim.html)
- dit
- dat
- dst

{% highlight html %}
<div>
  Completely destruction is my destiny!
</div>
{% endhighlight %}

## Problem

- I am using tmux, but I have multiple projects happening. Can I have multiple projects open. And how can I quickly switch between them?
- If I close my computer, all my tmux stuff would go away, is there a way to save my configurations?

## Solution
tmux sessions and tmuxinator to the rescue!  
Let's follow an example of a typical usecase of tmux and tmuxinator.  
We are going to create several sessions and switch between them.

1. `gem install tmuxinator`
1. C-a (control-a) *d* (detach from tmux)
1. Copy and paste these commands in your console (they all start with tm)

        alias tmo='tmuxinator open'
        alias tms='tmuxinator start'
        alias tmx='tmux attach || tmux'
        alias tml='tmux list-sessions'
        alias tmk='tmux kill-session -t'

1. tmo project-one  
   Use tmuxinator to create a yml file located at *~/.tmuxinator/my-project.yml*.

1. paste these lines in this file

        # ~/.tmuxinator/project-one.yml

        name: project-one
        root: ~/Work/project-one

        pre: mkdir -p ~/Work/project-one

        windows:
          - main:
              layout: main-vertical
              panes:
                - vim
                - c
                - c
          - config:

1. tms project-one
   Open a tmux session according to the yml file.
1. detach from tmux, create project-two and start a new tmux session.
1. C-a l to list all tmux sessions.
   j/k to navigate, enter to switch to the project.
1. detach again, use tml to list all tmux sessions
1. use tmx to re-enter latest tmux session
1. detach again, use ```tmk project-two``` to kill *project-two* session
1. use tml to list all tmux session
1. paste these aliases to `~/.stack.d/tmux.zsh`

## Exercise
create multiple tmux sessions using tmuxinator, switch between, then kill them.
