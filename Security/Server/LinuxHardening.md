# Linux Hardening

## General
- Less packages => Less vulnerability probablity (ex: no Xorg)
- Enable SELinux or Apparmor
- Prevent users from using old passwords

## Login
- Disable root login
- Disable password-based login and replace with key-based login
- Use fail2ban for limiting the number of unsuccessful logins

## Boot
- Disable other boot devices (DVD, CD, USB) in bios
- Set Firmware and GRUB password
- Disable `Ctrl+Alt+Delete` and prevent accidental reboot

## Network
- Check and keep only necessary open ports
- Change famous ports to an arbitrary number
- Setup iptables pessimistically
