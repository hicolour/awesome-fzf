# fzf is awesome
Simple utilities makes the biggest difference


### History

Search and paste to console
```
hs() { stty -echo && history | grep ""$@ | awk '{$1=$2=$3=""; print $0}' | fzf | xargs -I {} xdotool type {}  && stty echo; }
```

Search and execute to console
```
hsa() { history | awk '{$1=$2=$3=""; print $0}' | fzf | xargs -0 -I {} xdotool type {} ; }
```

# Process 

Process search and kill
```
psk() { ps -afx|  fzf |  xargs -0 -I {} echo {} | awk '{ printf $1 }' | xargs -0 -I {}  kill -9  {}; }
```

# Daily rutine 

Jump to the project dir

```
jp() { find ~/projects/ -maxdepth 3 -type d | fzf | xargs -0 -I {} xdotool type "cd {}" ; }
```
