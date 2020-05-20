# nmcli

Network Manager's Command line interface is absolutely amazing. It can control
all networking needs of a regular desktop user. Let's learn it.

## Overview

```bash
$ nmcli
```

## Device Info

To list the network devices:
```bash
$ nmcli dev
```
To see detailed list of devices:
```bash
$ nmcli dev show
```
To list wifi devices around you:
```bash
$ nmcli dev wifi list
```

## Connect to a network

To connect to a network:
```bash
$ nmcli dev wifi connect <ssid> password <pass>
```
To connect to a hidden network:
```bash
$ nmcli dev wifi connect <ssid> password <pass> hidden yes
```
To connect to `<ssid>` via the `<if>` interface:
```bash
$ nmcli dev wifi connect <ssid> password <pass> ifname <if>
```
To disconnect a device:
```bash
$ nmcli dev disconnect <if>
```

## Connection information

To see the saved connections:
```bash
$ nmcli con show
```
To activate a deactivated connection (or disconnected device):
```bash
$ nmcli con up <conn>
```
To deactivate a connection:
```bash
$ nmcli con down <conn>
```
To delete a saved connection:
```bash
$ nmcli con delete <conn>
```
Note that you must first get the exact `<conn>` from `nmcli con show` and not
rely on the `<ssid>` of your network because there may be multiple instances
of the same network.

## Wifi device control

To turn off a wifi device:
```bash
$ nmcli radio wifi off
```
To turn on a wifi device:
```bash
$ nmcli radio wifi on
```
To turn off all radio switches:
```bash
$ nmcli radio all off
```
To turn on all radio switches:
```bash
$ nmcli radio all on
```

## Create a bridge connection

First we must add a bridge-type connection:
```bash
$ nmcli con add type bridge ifname bridge0
```
Then we add a bridge slave and connect it to the physical NIC:
```bash
$ nmcli con add type bridge-slave ifname <if> master bridge0
```
Now we should bring down the "Wired connection" which is created by default
when connecting a wired cable and then bringing the newly created connection up:
```bash
$ nmcli con down "Wired Connection 1"
$ nmcli con up bridge-bridge0
```
If we like to have a certain short name (without the bridge-\* prefix) then:
```bash
$ sudo nmcli con add ifname br0 type bridge con-name br0
$ sudo nmcli con add type bridge-slave ifname <if> master br0
```
