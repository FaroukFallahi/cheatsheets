# tcpdump

To capture only a certain number of packets:
```bash
# tcpdump -c <num>
```

To see the actual packets (without their link layer header):
```bash
# tcpdump -A
```

To capture only packets from a certain interface:
```bash
# tcpdump -i <if-name>
```

To see the packets in hex format:
```bash
# tcpdump -xx
```

To filter packets from a certain port:
```bash
# tcpdump port <port-num>
```
