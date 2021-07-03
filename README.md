# Difference between terminal, shell, prompt and command line
## Terminal
A terminal, or terminal emulator, is a software program that lets you interact with the command line through your shell. The important part is that this is a GUI program.
## Shell
The shell is the program that reads your commands (like ls, pwd, etc) and evaluate them. Shells are mostly used as REPL (Read, Eval, Print, Loop). Meaning it is waiting for you to type something in its prompt and pressing Enter. Then it will evaluate the command and display a new prompt for you to type in a new command.
## Prompt
The prompt is simply the line that is displayed in your shell when you type a command. The default is usually something like user@host:/path/ $. This gets displayed at the start of each line and reminds you of who the current user is, on which machine and in which path.
## Command line
When someone tells you to "type something in the command line", it actually means "type something in your prompt, which is displayed by your shell, which is loaded by your terminal emulator". The command line is all this.

# Alias and functions
## Basics
```
alias h='cd ~'
alias c='clear'
alias ..='cd ..'
alias ls='ls -lach'
alias v.u='vagrant up'
alias v.h='vagrant halt'
alias v.r='vagrant reload'
alias v.s='vagrant ssh'
alias gd='cd /g/Mi\ unidad/' #Google Drive
alias w.hosts='/c/Windows/system32/drivers/etc/hosts' #Windows hosts file
```
## Vagrant Centos7
```
alias v.c7.u='cd ~/centos7 && vagrant up && vagrant ssh'
alias v.c7.h='cd ~/centos7 && vagrant halt'
alias v.c7.r='cd ~/centos7 && vagrant reload'
alias v.c7.s='cd ~/centos7 && vagrant ssh'
```
## Vagrant Homestead
```
alias v.h.u='cd ~/Homestead && vagrant up && vagrant ssh'
alias v.h.h='cd ~/Homestead && vagrant halt'
alias v.h.r='cd ~/Homestead && vagrant reload'
alias v.h.s='cd ~/Homestead && vagrant ssh'
```

# PHP
```
alias phpunit='vendor/bin/phpunit'

function pf(){
  phpunit --filter "$@"
}
```
# Customize
## Disable bell
```
bind 'set bell-style none'
```
## Show git branch in prompt
```
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

export PS1="\[\e[32m\]\u@\H - \[\e[32m\]\t \[\e[32m\]\w \[\e[36m\]\$(parse_git_branch) \[\e[00m\] \n \$ "
```
