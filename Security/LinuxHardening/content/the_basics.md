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
# vlock -c
```

See the `$ vlock -h` for more info (`-a` is pretty cool).

### Obscuring the system details at login

```bash
# clear > /etc/issue; \
  echo -e "\n\\d at \\\t\n" >> /etc/issue; \
  cp -f /etc/issue /etc/issue.net
```

```bash
# echo -e "\nWelcome.\n" > /etc/motd
```
Also make sure these files are `root:root 0600`.

## Users and Groups
Having usernames as a random string helps obscuring the correlation between
human beings (whom likes and attributes are easily recognizable) and their
usernames.

## Password

### Password difficulty
Enforcing password policies are made by using PAM's powers (Pluggable
Authentication Modules). In RH/Centos, we can modify `/etc/pam.d/passwd` which
itself points to `/etc/pam.d/system-auth`. But also, we can enforce our
policies through a command line application named `authconfig`:

```bash
# authconfig --enablereqlower \
  --enablerequpper \
  --enablereqdigit \
  --enablereqother \
  --passminlen=10 \
  --passmaxrepeat=3 \
  --update
```
First three options are self-explanatory, they enforce using uppercase, digit,
and other characters (symbols). `--passminlen=10` ensures at least 10
characters are provided. `--passmaxrepeat=3` ensures that no more than 3
consecutive repeated characters are entered. After running this command, you
can verify the settings by looking at the end of `/etc/security/pwquality.conf`
file.

### Password aging
To change a user's password aging, use the `chage` command:
```bash
# chage <user>
```

And to change the defaults, edit the `/etc/login.defs`:

```
PASS_MAX_DAYS	365
PASS_MIN_DAYS	0
PASS_WARN_AGE	7
```

## Sudo
Users must only be using sudo when required to execute root-privileged
commands. Here are some notes:

- `<user> <host>=(<user_to_run_command_as>) <command>`
- `%groupname ALL=(ALL) ALL`  (allows users of <groupname> to run any command
on any host
- `User_Alias ADMINS = <user1>,<user2>,...`
- `Cmnd_Alias CRITICAL = <command1>,<command2>,...`
- `Host_Alias CORE = <host1>,<hos2>,...`
- `ADMINS CORE=CRITICAL`
- `regular_user CORE=!CRITICAL` (deny access to those critical commands on core
servers to a regular user)
- `admin_user ALL = (another_user) some_command` (allows admin to run some
command as another user)

## User Accounting
To get a list of logged in users and a bit more info about system:
```bash
# who
# who -aH
```

To see the list of user logins and reboot:
```bash
# last
```

And to see the "bad" user logins:
```bash
# lastb
```

And to see most recent login of users:
```bash
# lastlog
```

## Process Accounting
On rpm based distros use `psacct` and on deb based ones `acct`.

```bash
# lastcomm
# lastcomm --user <user>
# lastcomm --tty <tty>
# lastcomm --command <command>
# ac
# ac -d
# ac -p
# ac <user>
# ac -d <user>
# sa  (re==real time, cp==cpu time)
# sa -u
# sa -m
# sa -c
```
