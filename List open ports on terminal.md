Use `netstat` to see incoming connection ip

```bash
netstat -atp tcp | grep -i "listen"
Achive Internet connections (including servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp4       0      0  localhost.25035        *.*                    LISTEN
```

Use `lsof` to get the process id

```bash
lsof -i -P | grep -i "listen"
COMMAND     PID      USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
GitHub      850 grgarside   6u   IPv4 0x23c345381d089301      0t0  TCP localhost:25035 (LISTEN)
```

Handy commands

- `lsof -i -P | grep LISTEN`
- `netstat -nltup`
- `ss -nltupw`

## See also
- [[Check if port is open and open ports]]