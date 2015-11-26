title: 'Solved: no tty present and no askpass program specified'
date: 2015-11-26 07:37:11
tags:
---
Run visudo with nano (I prefer it over vi) or with the editor you want:
``` bash
$ EDITOR=nano sudo visudo
```
Next, type something like this at the end of the file:
``` bash
$ username ALL = NOPASSWD: /fullpath/to/command, /fullpath/to/othercommand
```
For example:
``` bash
$ zheref ALL = NOPASSWD: /Users/zheref/.nvm/versions/node/v3.2.2/bin/npm, /Users/zheref/.nvm/versions/node/v4.2.2/bin/node
```
Save and exit.

I must clarify, even doing that it didn't work for Node/NPM. That message is not appearing anymore, but
NPM is still requiring root permissions to run.