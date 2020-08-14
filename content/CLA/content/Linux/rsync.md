# rsync

## To backup files into an external drive

```bash
$ rsync -avu --delete /home/user/InternalHDD/* /run/media/user/ExternalHDD
```

This causes `rsync` to use `-a` so it archives the files (keeps their properties and operate recursively on them), it also `-v`erboses the files it's operating on and then `-u`pdates the files (skip the ones that are newer on the destination and only backup the ones that have some difference in size if they have the same timestamp as the ones in destination). Finally `--delete` causes the files on destination to be deleted if they are not present in the source as well.

Or:

```bash
$ rsync -au --progress --delete /home/user/InternalHDD/ /run/media/user/ExternalHDD/
```
