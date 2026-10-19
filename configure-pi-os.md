# Configure Pi OS

To save your changes when editing a file in nano press: Ctrl+x then Y then `<enter>`.

## Update OS

```
sudo apt update
sudo apt full-upgrade
```

## Remove the rainbow screen at start up

`sudo nano /boot/firmware/config.txt`

Add the following lines:

```
[all]
disable_splash=1
```

## Set boot options

### Set quiet boot

`sudo nano /boot/firmware/cmdline.txt`

Add the following to the end of the line (keep everything on one line)

```
splash quiet loglevel=0 logo.nologo vt.global_cursor_default=0
```

### Limit the amount of login message text

```
sudo rm /etc/motd
sudo truncate -s 0 /etc/issue
sudo truncate -s 0 /etc/issue.d/IP.issue
```

`sudo nano /etc/pam.d/login`

Comment out the following lines:

```
session    optional   pam_motd.so  motd=/run/motd.dynamic
session    optional   pam_motd.so  noupdate
```

### Remove Cloud init (optional)

```
sudo apt purge cloud-init -y
sudo rm -rf /etc/cloud /var/lib/cloud
sudo apt autoremove
```

## Setup USB

### Get USB partition name

```
lsblk
```
Make a note of the USB partition name, e.g. sda1

### Create mount point

```
sudo mkdir -p /mnt/usb
```

### Mount USB

```
sudo mount /dev/sda1 /mnt/usb
```

### Unmount USB

```
sudo umount /dev/sda1
```

### Boot performance optimisations (optional)

These are optional settings to optimise boot up speed.

#### Disable NetworkManager-dispacher

```
sudo systemctl stop NetworkManager-dispatcher.service
sudo systemctl disable NetworkManager-dispatcher.service
```

#### Disable rpi-eeprom-update.service

```
sudo systemctl stop rpi-eeprom-update.service
sudo systemctl disable rpi-eeprom-update.service
```

## Reboot

Reboot the Raspberry and check it boots ok.

Type: reboot `<enter>`

## Next Step - Install Amiberry

[Install Amiberry](install-amiberry.md)

