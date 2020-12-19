# How to Count Files in Directory in Linux
 
 There are times when you need to find out how many files are in a given directory. For example, if you run out of `inodes`
 on your Linux system,
 you’ll need to find which directory contains thousands or millions of files.
 
 The simplest way to count files in a directory is to list one file per line with `ls` and `pipe` the output to `wc` 
 to count the lines:
 
 ```bash
$ ls -1U DIR_NAME | wc -l
 ```
The command above will give you a sum of all files, including `directories` and `symlinks`. 
The `-1` option means list one file per line 
and `-U` tells ls to do not sort the output which makes the execution of the command faster.

`ls -1U` command doesn’t count hidden files (dotfiles).

If you want to count only files and not include the directories use the following:

```bash
$ ls -1Up DIR_NAME | grep -v / | wc -l
```
list all the files and use `grep` to search the output  for the ones that don't have '/'

The `-p` option forces `ls` to append slash (/) indicator to directories. 
The output is `piped` to the `grep -v` command that exclude the directories.

To have more control over what files are listed, use the `find` command instead of `ls`:
```bash
$ find DIR_NAME -maxdepth 1 -type f | wc -l
```

`-type f` option tells `find` to list only files (including dotfiles), and `-maxdepth 1`
limit search to the first-level directory.

## Recursively Count Files in Directory 

To recursively count files in directory run the find command as follows:

```bash 
$ find DIR_NAME -type f | wc -l
```

Another command that can be used to count files is `tree` that lists contents of directories in a `tree-like format`:

```bash
$ tree DIR_NAME
```

The last line of output will show the total number of files and directories listed:

```bash
$ tree DIR_NAME | tail -1
```



