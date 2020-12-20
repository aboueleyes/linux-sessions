## This list will b updatd regulary 

Execute a command at a given time
```bash
$ echo "ls -l" | at midnight
```

Quick access to the ascii table.
```bash
$ man ascii
```
Put a console clock in top right corner

```bash
$ while sleep 1;do tput sc;tput cup 0 $(($(tput cols)-29));date;tput rc;done &
```

Matrix Style
```bash
$ tr -c "[:digit:]" " " < /dev/urandom | dd cbs=$COLUMNS conv=unblock | GREP_COLOR="1;32" grep --color "[^ ]"
```

replace spaces in filenames with underscores
```bash
$ rename 'y/ /_/' *
```

Generate a random password 30 characters long
```bash
$ strings /dev/urandom | grep -o '[[:alnum:]]' | head -n 30 | tr -d '\n'; echo
```

pretend to be busy 
```bash
$ cat /dev/urandom | hexdump -C 
```
Makes the permissions of file2 the same as file1
```bash
$ chmod --reference file1 file2
```

Nice weather forecast on your shell
```
$ curl wttr.in/cairo
```
Convert Youtube videos to MP3
```bash
$ youtube-dl -t --extract-audio --audio-format mp3 YOUTUBE_URL_HERE
```
