# Setup Pi OS

## Write the Pi OS image to a microSD card

Use the Raspberry Pi Imager to install Pi OS with the following options.

### Device 

Raspberry Pi 4

### OS

Raspberry Pi OS (64bit)
A port of the Debian Trixie with the Raspberry Pi Desktop

### Storage

Select your microSD storage device.

### Customisation

#### Choose hostname

A unique name that identifies your Raspberry Pi on the network.

```
amiga-pi400
```

#### Localisation

Set your localisation prefernces.

```
Capital city: London (United Kingdom)
Time zone: Europe/London
Keyboard Layout: gb
```

#### User

Set your own username / password

```
Username: xxx
Password: xxx
```

#### Wifi

Set up Wifi

```
SSID: xxx
Password: xxx 
```

#### Remote access

Enable SSH if required.

```
Enable SHH: Off
```

#### Raspberry Pi Connect

Enable Raspberry Pi Connect if required

```
Enable Raspberry Pi Connect: Off
```

### Write image

Check settings and write image to the microSD.

Note: This will erase everything on the microSD card.

## Configure Pi OS

Insert the microSD card into the Raspberry Pi 400 and configure the following settings

Open the Control Centre (available under the preferences menu)

### System

Set the following options to automatically login to the command line only.

Only the following options are needed to be set, the rest can be left as default.

```
Boot: To CLI
Console auto login: On
Splash Screen: On

```

### Reboot to CLI

Reboot the Raspberry Pi and check it boots into the CLI and not the desktop.




### Boot performance optimisations

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
