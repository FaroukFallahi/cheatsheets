# fstab
This file is probably useless for general users, but i'm too lazy to check Arch
Wiki for proper configuration, so i just note these configs that i use on a
regular basis:

## for an ext4 filesystem
```bash
UUID=<uuid> <mount-point> ext4 defaults,nofail,x-systemd.device-timeout=1 0 2
```

## for ntfs filesystem
```bash
UUID=<uuid> <mount-point> ntfs permissions,locale=en_US.utf8
```

## for an encrypted ext4 filesystem (dm_crypt)
First we should add this to our fstab file:
```bash
/dev/mapper/mzd <mount-point> ext4 defaults,errors=remount-ro 0 2
```
Then we can add this to our `/etc/crypttab`:
```bash
mzd UUID=<uuid> <key-file-location> luks,timeout=180
```
Note that we must store our key like this:
```bash
# echo -n "somepass" > /path/to/key
# chown root:root /path/to/key
# chmod 400 /path/to/key
```
