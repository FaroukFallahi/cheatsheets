# cryptsetup

## create encrypted disk
This section is not completed now!

## To open an encrypted disk
First we must open the disk:
```bash
# cryptsetup open /dev/sdX someName
```
Then, we can mount the mapper device associated with `someName`:
```bash
# mount -t ext4 /dev/mapper/someName /mnt
```

## To close an encrypted disk
First, unmount:
```bash
# umount /mnt
```
Then we can close the disk:
```bash
# cryptsetup close someName
```
