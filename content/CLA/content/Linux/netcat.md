# netcat
netcat establishes a connection to a specific ip/port. Also, there is another
alias for it called `nc` (they both are symbolic links to `nc.openbsd`)

To get the content of a web page (doesn't work for https):
```bash
# nc www.google.com 80
> GET / HTTP/1.1
> (enter once more to complete the header)
```

To create somewhat client/server and test connections. On the server side:
```bash
$ netcat -l -p <port-number>
```
And on the client side:
```bash
$ netcat <ip-number> <port-number>
```
