---
layout: default 
title: Bash scripting 
---

# Bash scripting 

You can write your own shell commands to make your workflows more efficient! Follow [this tutorial](https://medium.com/devnetwork/how-to-create-your-own-custom-terminal-commands-c5008782a78e) and [these docs](https://ryanstutorials.net/bash-scripting-tutorial/bash-script.php). 

For example, type the following function in your terminal 
```
function print_arg() {
 echo 'Your argument: ' $1
}
```
and now type `$ print_arg "my arg"` and the output will be `Your input:  my arg`.  
