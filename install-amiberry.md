# Install Amiberry

## Amiberry

```
curl -fsSL https://packages.amiberry.com/install.sh | sudo sh
sudo apt install amiberry
```

## Amiberry Lite

Download [amiberry-lite-v5.9.4-debian-trixie-arm64.zip](https://github.com/BlitterStudio/amiberry-lite/releases/download/v5.9.4/amiberry-lite-v5.9.4-debian-trixie-arm64.zip) to ./

Copy it to your home directory and run the following command:

```
sudo apt install ./amiberry-lite_5.9.4+trixie_arm64.deb
```

## Set amiberry to auto start

```
nano ~/.bashrc
```


## Install PipeWire

```
sudo apt install pipewire
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
