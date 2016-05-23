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
- Ssh agent
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
Meta-. (Alt-.)
    Insert the last argument of the previous command
```

Tip for iTerm user (Preference > Profile > Keys):

<center>
<img src="img/readline-iterm.jpg" />
</center>

Ref: https://en.wikipedia.org/wiki/GNU_Readline

---

class: center, middle

## Ssh agent

Never type password again

---

class: center, middle

## Git config

Make version control easier

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
