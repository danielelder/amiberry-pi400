# Amiberry Raspberry Pi-400

## Setup OS

### Install OS

Install Raspberry Pi OS Lite 64bit on to the microSD card [using imager](https://www.raspberrypi.com/documentation/computers/getting-started.html#imager-install)

```
sudo apt update
```

### Remove Splash screen

`sudo nano /boot/firmware/config.txt`

```
[all]
disable_splash=1
```
### Set boot options

#### Set quiet boot

`sudo nano /boot/firmware/cmdline.txt`

Add the following to the end of the line (keep everything on one line)

```
quiet logo.nologo
```

#### Set automatic login
Run `sudo raspi-config`

```
System Options -> Auto Login -> Yes
```

#### Remove Cloud init

```
sudo apt purge cloud-init -y'
sudo rm -rf /etc/cloud /var/lib/cloud
sudo apt autoremove
```
*Reboot*

## Install Amiberry

```
curl -fsSL https://packages.amiberry.com/install.sh | sudo sh
sudo apt install amiberry
```

## Install PipeWire

```
sudo apt install pipewire
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

## Install Kickstart roms

```
Copy roms from /mnt/usb/...

cp /mnt/usb/Kickstart/kick40068.a1200 /home/user/Amiberry/ROMSs/
```

## Install Workbench

```
cp /mnt/usb/Workbench/* /home/user/Amiberry/Floppies/
```

