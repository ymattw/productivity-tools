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
- Shell config
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

Do you type this often?

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

## Shell config

Saves your fingers

---

### Bash PS1

Do you often type `pwd`, `git status`, `git branch` from bash command line?

Or often type `echo $?` to tell exit status from last command?

Let $PS1 do that automatically!

<img src="img/bash-ps1.jpg" />

---

### Customize .bashrc

Refer to [Controlling the Prompt](https://www.gnu.org/software/bash/manual/bashref.html#Controlling-the-Prompt)

```
\h  The hostname, up to the first '.'
\H  The full hostname
\t  The time, in 24-hour HH:MM:SS format
\T  The time, in 12-hour HH:MM:SS format
\u  The username of the current user
\w  The current working directory
\W  The basename of $PWD
\$  If the effective uid is 0, #, otherwise $
```

---

### Special notes

Want ANSI color?  Refer to [ANSI escape code](https://en.wikipedia.org/wiki/ANSI_escape_code).

```
\e[31m denotes foreground red
\e[0m  resets ansi color
```

Cool, but note you need to <span class="red">surround
non-printable chars with `\[` and `\]`</span>, otherwise your command
line will be in a mess when it is wrapped to next line!

```
\]
    Begin a sequence of non-printing characters. This could be used to
    embed a terminal control sequence into the prompt.

\]
    End a sequence of non-printing characters.
```

---

### Bash PS1 example

Example:

```bash
PS1="\$([[ \$? == 0 ]] && echo '${_DG}✔' || echo '${_DR}✘') \t "
...
PS1="${PS1}$(hostname -f)"
PS1="${PS1}:\[\e[33m\]\w\[\e[0m\]"  # yellow cwd
PS1="${PS1}\$(_git_active_branch)"  # git branch name
```

You can do much more.  See also my
[bashrc](https://github.com/ymattw/profiles/blob/master/bash/bashrc#L185-L219).

---

### Zsh

[zsh](https://en.wikipedia.org/wiki/Z_shell): Shell for Pros

- Powerful completion
- Sharing history among all instances
- Spell correction
- Themeable prompts
- Loadable modules

Refs:

- [What are the cool features of zsh that beat other
  shells?](https://www.quora.com/What-are-the-cool-features-of-zsh-that-beat-other-shells)
- My [zshrc](https://github.com/ymattw/profiles/blob/master/zsh/zshrc)

---

### Fish shell

[fish](https://fishshell.com/): Finally, a command line shell for the 90s (not
for me :-)

- Syntax highlighting
- Autosuggestions
- Sane Scripting
- (90s want to be cool)

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
