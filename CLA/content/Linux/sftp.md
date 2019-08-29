# sftp
Secure file transfer program. It's just amazing when moving files on the
internet, say between your own computer and the server you must put some
file on.

Connect just like you connect via ssh:
```bash
$ sftp user@host
```

Use ls and lls (local ls) to view the files:
```bash
> lls
```

And the cd and lcd (local cd) to change directories:
```bash
> lcd ~/path/to/file
```

Upload a file to the remote computer:
```bash
> put ~/path/to/local/file
```

Download a fiel from the remote computer:
```bash
> get ~/path/to/remote/file
```
