# Hardening the basics

## Boot

### BIOS

- Enable password protection in BIOS

### Bootloader
Physical access to a linux system can jeopardize it's security big time! To
help securing a linux system, we can set a password for GRUB so that only
`root` user using that specific password can modify (for instance boot in
single-user-mode) boot entries. Note that this saves the password in sha512 so
we're good to go :)

links:
[Redhat article on GRUB 2 password protection](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/sec-protecting_grub_2_with_a_password)

### Package/Service minimalism
Less packages => Less vulnerability probablity.

- Remove Xorg/Wayland, there should be no GUI since we can survive via CLI
- Take a look at `$ systemctl -a` and take down the unnecessary services
  (also packages)

## Consoles

### Allow root to login only on tty1
Edit the file `/etc/securetty` and comment all but `tty1`:

```bash
...
#vc/11
tty1
#tty2
...
```
Also make sure that file is `root:root 0600`.

### Make sure non-root users are not over-privileged
The files in `/etc/security/console.apps` are available to non-root users
iff they login via console, but this is a bad practice so make sure that
directory is empty. Also check the `/etc/security/console.perms.d` along
with `/etc/security/console.perms` for permissions.

### Locking virtual terminals
Using the `vlock` program, we can lock our VTs, for instance to lock the
current VT:

```bash
$ vlock -c
```

See the `$ vlock -h` for more info (`-a` is pretty cool).

### Obscuring the system details at login

```bash
$ clear > /etc/issue; \
  echo -e "\n\\d at \\\t\n" >> /etc/issue; \
  cp -f /etc/issue /etc/issue.net
```

```bash
$ echo -e "\nWelcome.\n" > /etc/motd
```
Also make sure these files are `root:root 0600`.

## Users and Groups
Having usernames as a random string helps obscuring the correlation between
human beings (whom likes and attributes are easily recognizable) and their
usernames.
