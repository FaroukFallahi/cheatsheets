# netstat
Network Status?! Well it's being replaced by other commands but we may use it
for quite a time, so i just write the cheatsheet anyway.

To list the listening sockets:
```bash
# netstat -l
```

To see the port numbers instead of the program's name:
```bash
# netstat -ln
```

To see all sockets:
```bash
# netstat -a
```

To see the program's PID and name:
```bash
# netstat -p
```

To see the kernel's routing table:
```bash
# netstat -r
```

To see the interface statistics:
```bash
# netstat -i
```

To see the tcp ports:
```bash
# netstat -t
```

To see the udp ports:
```bash
# netstat -u
```
