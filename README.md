# RaspberryPi Image Shrinkwrap and PI Shrink for OrangePi

I use this this repo for shrinking ready made images of talkkonnect for distribution.

NOTE: USE AT OWN RISK - THIS IS UNTESTED. ALWAYS BACKUP YOUR IMAGE BEFORE TRYING
THIS.

## Copy the sd card over 

Find your sdcard device, might be /dev/sdb or /dev/mmcblk0 or other.

```bash
lsblk
```

Copy the image locally to an img file 
```bash
sudo dd bs=4M if=/dev/mmcblk0 of=myimage.img conv=fsync status=progress
```

## Shrink the image (Raspberry Pi) or
```
./shrinkwrap.sh myimage.img
```

## Shrink the image (Orange Pi)
```
./pishrink.sh myimage.img
```

## Copy the image to new sd card or use Raspberry Pi Imaging tool
```bash
sudo dd bs=4M if=myimage.img of=/dev/mmcblk0.img conv=fsync status=progress
```

## Boot from the card 

You can now resize the image back to take the full SD card size by going to:

```
sudo raspi-config
```

And then choose "Expand root partition to fill SD card" option under Advanced 
Options.
