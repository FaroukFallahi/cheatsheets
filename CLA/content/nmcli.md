# nmcli

Network Manager's Command line interface is absolutely amazing. It can control
all networking needs of a regular desktop user. Let's learn it.

## Overview

```bash
$ nmcli
```

## Device Info

* To list the network devices: `$ nmcli dev`
* To see detailed list of devices: `$ nmcli dev show`
* To list wifi devices around you: `$ nmcli dev wifi list`

## Connect to a network

* To connect to a network:
`$ nmcli dev wifi connect <ssid> password <pass>`
* To connect to a hidden network:
`$ nmcli dev wifi connect <ssid> password <pass> hidden yes`
* To connect to `<ssid>` via the `<if>` interface:
`$ nmcli dev wifi connect <ssid> password <pass> ifname <if>`
* To disconnect a device:
`$ nmcli dev disconnect <if>`

## Connection information

* To see the saved connections:
`$ nmcli con show`
* To activate a deactivated connection (or disconnected device):
`$ nmcli con up <conn>`
* To deactivate a connection:
`$ nmcli con down <conn>`
* To delete a saved connection:
`$ nmcli con delete <conn>`

## Wifi device control

* To turn off a wifi device:
`$ nmcli radio wifi off`
* To turn on a wifi device:
`$ nmcli radio wifi on`
* To turn off all radio switches:
`$ nmcli radio all off`
