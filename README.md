# LC-Exercises
This is a  series of exercises. Some give you a specific task to do, while others are open-ended, We highly recommend  you to try them out.
## shell 
for this tutorial you you need a Unix shell like bash or zsh, if you are on Linux , you don't have to do anything 
for windows you can use [Windows Subsystem for
    Linux](https://docs.microsoft.com/en-us/windows/wsl/) or a Linux virtual
    machine to use Unix-style command-line tools.
##  Exersice 1 
1. make a directory called `LC`  in your home dir 
2. use `touch` to create a new file called `test` in your `LC` dir 
3. write the following into that file 
    ```
    #!/bin/sh
        curl --head --silent https://www.google.com/
    ```
The first line called `shebang` (look it up !)
what is `sh` ? how it is different from `bash` ? look it up and you can try something like `fish` or `zsh` 

4. Try to execute the file, i.e. type the path to the script `(./test)` into your shell and press enter. Understand why it doesn’t work by consulting the output of `ls` (hint: look at the permission bits of the file). is it executable ?

5. Run the command by explicitly starting the `sh` interpreter, and giving it the file test as the first argument, i.e. `sh test`. Why does this work, while .`/test` didn’t?

6. Look up the `chmod` program (e.g. use `man chmod`).

7. Use chmod to make it possible to run the command `./test` rather than having to type `sh test`. How does your shell know that the file is supposed to be interpreted using `sh`?

8. make a python file called `testpy` , in the same manner make the file print "hello world" when executing it `./testpy`

9. what is the diiference between `>` and `>>` explain with exapmles 

10. we talked about aliases. it is very common to alias `ll` to `ls -alh` How can you do it ?

Note : This is a markdown file , it is very easy to use, search how to use it. 

## Exersice 2 
1. Follow this `tmux` [tutorial](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

*oprional*
then learn how to do some basic customizations following [these steps.](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

2. explore the `fzf` program you can easily install it with apt run `fzf` what does it do ?

you can do alot of things check this [tutorial](https://www.freecodecamp.org/news/fzf-a-command-line-fuzzy-finder-missing-demo-a7de312403ff/)

3. try running `apt install vim` problem right ? so after it run `sudo !!` what just happen, try to guess and search for it , try `!15`

4. run `histroy` what does it do ? search for advanced usage. how about `cat ~/.bash_history` what does this file contain? finally press `ctrl + r`. type something. can fzf be integrated here ?

5. what is `symoblic links`? how to make them? think of examples when they are useful ?

*optional* search for `hard links` how they differ from `symbolic links`
after creating a `link` run `ls -l` what do you notice ? 

6- what does `diff` command do ? how it is useful ? what about `patch`
