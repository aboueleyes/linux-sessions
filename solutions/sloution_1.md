# Exersice 1
### 1. Make a directory called LC in your home dir
#### Answer : bash 
`$ mkdir Lc && cd LC`
### 2. Use touch to create a new file called test in your LC dir
#### Answer :
`$ touch test`
### 3. Write the following into that file
#### Answer : 
`$ echo '#!/bin/bash' > test `

`$ echo "curl --head --silent google.com" >> test`

 [sh and bash](https://stackoverflow.com/questions/5725296/difference-between-sh-and-bash) 
 
 ### 4. Try to execute the file, i.e. type the path to the script `(./test)` into your shell and press enter. Understand why it doesn’t work by consulting the output of `ls` (hint: look at the permission bits of the file). is it executable ?
 
 #### Answer :
 `$ ./test `
 
 `$ ls -l`

The permission string is `-rw-r--r--`, so my user is not allowed to execute this file.

### 5. Run the command by explicitly starting the `sh` interpreter, and giving it the file test as the first argument, i.e. `sh test`. Why does this work, while .`/test` didn’t?

#### Answer : 
calling `sh test`, the file `test` is passed as an argument to the `sh` program, which will interpret this file. Even though we don't have permition to run `test`, we do are allowed to run `sh`.

###  7. Use chmod to make it possible to run the command `./test` rather than having to type `sh test`. How does your shell know that the file is supposed to be interpreted using `sh`?
#### Answer : 
 to give all permitions to the creator user, but only read permission to the group and other users, we use the command:

`chmod 744 test`

As the first line in the file is `#!/bin/sh` , the program loader is instructed to run the file with `/bin/sh`.

### 8. make a python file called `testpy` , in the same manner make the file print "hello world" when executing it `./testpy`
#### Answer :
`$ echo '#!/bin/python3' > test.py `

`$ echo "print("Hello World!")" >> test.py`

`$ chmod 755 ./test.py`

`$ ./test.py `

### 9. what is the diiference between `>` and `>>` explain with exapmles 
#### [Answer](https://serverfault.com/questions/196734/bash-difference-between-and-operator#:~:text=3%20Answers&text=The%20%3E%20sign%20is%20used%20for,if%20it%20doesn't%20exist.)

### 10. we talked about aliases. it is very common to alias `ll` to `ls -alh` How can you do it ?
#### Answer : 

`$ echo "alias ll='ls-alh'" >> ~/.bashrc`

`$ source ~/.bashrc`

`$ ll`


