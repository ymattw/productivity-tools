class: center, middle

# Productivity Tools

<img src="img/tools.jpg" />

Matthew Wang

<small>
Last updated: May 24, 2016<br>
[github.com/ymattw](https://github.com/ymattw)
</small>

---

class: center, middle

## Preface

Why tools matter

---

## Outline

- Readline
- Ssh config
- Git config
- Bash PS1
- Zsh / fish
- Screen / tmux
- Vim plugins
- Mosh

---

class: center, middle

## Readline

Speed up your command typing

---

### GNU readline

[Readline](https://cnswww.cns.cwru.edu/php/chet/readline/rltop.html) is not
a command, it's a library for line editing used by most command line
interfacing tools.  Try in bash and mysql session.

Cursor moving:

```
C-a
    Moves the cursor to the line start (key Home)

C-e
    Moves the cursor to the line end (key End)

Alt-b
    Moves the cursor backward one word

Alt-f
    Moves the cursor forward one word
```

---

### GNU readline (cont.)

Line editing:

```
C-w
    Clears the word before the cursor

C-u
    Clears the line content before the cursor

C-d
    Delete the character underneath the cursor.

C-x C-e
    Edits current line with $EDITOR, or vi if undefined

C-r
     Reverse search command in history, a second Ctrl+r repeats

C-s
    Go back to the next more recent command of the research
    (Pro tip: Add test -t 0 && stty stop undef to your .bashrc)
```

---

### GNU readline (cont.)

```
Meta-. (Alt-.) or ESC-.
    Insert the last argument of the previous command
```

Tip for iTerm user (Preference > Profile > Keys):

<center>
<img src="img/readline-iterm.jpg" />
</center>

Ref: https://en.wikipedia.org/wiki/GNU_Readline

---

class: center, middle

## Ssh config

Never type password again

---

### Ssh key

Setup a key-pair if you haven't, secure it with a **passphrase**!

```bash
ssh-keygen -t rsa -b 2048
```

Install it to remote host

```bash
ssh-copy-id user@host
```

_But it asks me to input passphrase everytime?_

---

### Use ssh with an agent

3 ways to invoke the daemon

- `ssh-agent bash`
- `eval $(ssh-agent)`
- `ssh-agent > ~/.ssh-agent.rc && source ~/.ssh-agent.rc`

Add key (asks passphrase once)

- `ssh-add [~/.ssh/id_rsa]`

Use (ssh will ask the agent for the key)

- `ssh user@host`

---

### Save ssh options in config file

Do you type this a lot of time?

```
ssh -l ymattw -p 2200 -i ~/.ssh/ymattw.key 192.168.1.2
```

Use ~/.ssh/config

```
Host dev
    Hostname 192.168.1.2
    Port 2200
    Username ymattw
    IdentityFile ~/.ssh/ymattw.key

Host *
    User me
```

Now just type `ssh dev`

See all options: `man ssh_config`

More tips see https://ymattw.github.io/ssh-essential/

---

class: center, middle

## Git config

Make version control easier

---

### Git alias

Less key strokes:

```bash
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.info "remote -v show -n"
git config --global alias.br branch
git config --global alias.co checkout
```

See more in my [gitconfig.sh](https://github.com/ymattw/profiles/blob/master/git/gitconfig.sh).

---

### Useful config

```bash
# Use vim to edit commit log
git config --global core.editor vim

# Be colorful
git config --global color.ui true

# Use short commit hash
git config --global log.abbrevcommit true

# Show readable symbol for comm
git config --global log.decorate short

# Show foo/bar.c instead of [ab]/foo/bar.c
git config --global diff.noprefix true
```

See more in my [gitconfig.sh](https://github.com/ymattw/profiles/blob/master/git/gitconfig.sh).

---

class: center, middle

## Bash PS1

Saves you lots of time

---

class: center, middle

## Zsh / fish

Shell for Pro's

---

class: center, middle

## Screen / tmux

You need only one terminal window

---

class: center, middle

## Vim plugins

Be a vim guru

---

class: center, middle

## Mosh

Connection allows roaming

---

class: center, middle

## Thank you!

[github.com/ymattw/productivity-tools](https://github.com/ymattw/productivity-tools)
