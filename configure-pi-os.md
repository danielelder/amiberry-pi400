# Configure Raspberry Pi-400

## Update OS

```
sudo apt update
```

## Remove the rainbow screen at start up

`sudo nano /boot/firmware/config.txt`

```
[all]
hdmi_enable_4kp60=1
disable_splash=1
```

*Note:* to save and exit nano press: Ctrl+x then Y then `<enter>`.


## Set boot options

### Set quiet boot

`sudo nano /boot/firmware/cmdline.txt`

Add the following to the end of the line (keep everything on one line)

```
quiet logo.nologo
```

### Remove Cloud init (optional)

```
sudo apt purge cloud-init -y
sudo rm -rf /etc/cloud /var/lib/cloud
sudo apt autoremove
```

## Reboot

Reboot the Raspberry and check it boots ok.

Type: reboot `<enter>`

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

cp /mnt/usb/Workbench/* /home/user/Amiberry/Floppies/
```

