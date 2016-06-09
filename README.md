# git-commands
Various git-commands I use

To shadow default git commands, I use a function adapted from [this SO answer](http://stackoverflow.com/a/16410521/919057) in my `.bashrc`. For example, to shadow `git status` with `git statuscm`.


```
function do_git {
  cmd=$1
  shift
  if [ "$cmd" == "status" ]; then
    cmd="statuscm"
  #elif [ "$cmd" == "other default command" ]; then
  #  cmd="custom command"
  fi
  "$(which git)" "$cmd" "$@"
}
alias  git='do_git'
```
