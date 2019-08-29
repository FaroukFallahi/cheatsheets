# nmap

To scan a target:
```bash
# nmap <ip>
```

Multiple ip addresses:
```bash
# nmap 192.168.1.1,4
# nmap 192.168.1-10
```
Here the first command scans `192.168.1.1` and `192.168.1.4` but the second
	one scans from `192.168.1.1` to `192.168.1.10`.

To read the IPs from a file:
```bash
# nmap -iL ~/path/to/file
```

To list all devices in network (ping scan):
```bash
# nmap -sn 192.168.1.0/24
```

To list the OS details:
```bash
# nmap -A <ip>
```
