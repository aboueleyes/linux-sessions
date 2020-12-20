# How to Recursively Change the File's Permissions in Linux

## Chmod Recursive
The `chmod` command allows you to change the permissions of files using `symbolic` or `numeric` mode

To recursively operate on all files and directories under a given directory, use the chmod command with the `-R`, (`--recursive`) option. 
The general syntax to recursively change the file’s permissions is as follows:

```bash
chmod -R MODE DIRECTORY
```
 For example, to change the permissions of all files and subdirectories under the `/var/www/html` directory to `755` you would use:
```bash 
$ chmod -R 755 /var/www/html
```
The mode can also be specified using the symbolic method:

```bash
$ chmod -R u=rwx,go=rx /var/www/html
```
Only root, the file owner, or user with `sudo` privileges can change the permissions of a file. Be extra careful when recursively changing the files' permissions.

## Using `find` command

In general, the files and directories should not have the same permissions. Most files do not require the execute permission, whereas you must set execute permissions on the directories in order to change into them.

The most common scenario is to recursively change the website file’s permissions to `644` and directory’s permissions to `755`.

Using the `numeric` method:

```bash
$ find /var/www/html -type d -exec chmod 755 {} \;
$ find /var/www/html -type f -exec chmod 644 {} \;
```

Using the `symbolic` method:

```bash
$ find /var/www/html -type d -exec chmod u=rwx,go=rx {} \;
$ find /var/www/html -type f -exec chmod u=rw,go=r {} \;
```
The `find` command searches for files or directories under `/var/www/html` and passes each found file or directory to the `chmod` command to set the permissions.

When using `find` with `-exe`c, the `chmod` command is run for each found entry. Use the `xargs` command to speed up the operation by passing multiple entries at once:

```bash
$ find /var/www/html -type d -print0 | xargs -0 chmod 755 
$ find /var/www/html -type f -print0 | xargs -0 chmod 644
```

