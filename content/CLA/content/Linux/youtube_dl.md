# Youtube Downloader

To use a proxy (here tor):
```bash
$ youtube-dl --proxy="socks5://127.0.0.1:9050" <url>
```

To get all availabie qualities and formats:
```bash
$ youtube-dl -F <url>
```

To select a specific entry (<num> is the first column that `-F` lists):
```bash
$ youtube-dl -f <num>
```
