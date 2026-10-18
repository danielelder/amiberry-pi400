Install standard image


disable NetworkManager-dispacher

```
sudo systemctl stop NetworkManager-dispatcher.service
sudo systemctl disable NetworkManager-dispatcher.service
```
Disable rpi-eeprom-update.service

```
sudo systemctl stop rpi-eeprom-update.service
sudo systemctl disable rpi-eeprom-update.service
```
