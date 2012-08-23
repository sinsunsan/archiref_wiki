### The sudoers files 

* http://www.garron.me/linux/visudo-command-sudoers-file-sudo-default-editor.html
```
vim /etc/sudoers
```

* This line means: The root user can execute from ALL terminals, acting as ALL (any) users, and run ALL (any) command.
```
root ALL=(ALL) ALL
```

* Editer le fichiers visudo avec vim 
```
export VISUAL=vim; visudo
```


