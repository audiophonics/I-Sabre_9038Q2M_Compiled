# I-Sabre_9038Q2M_Compiled
I-sabre 9038Q2M driver Compiled for specific kernel version

# Installation

##Install Minizip :
sudo apt-get install minizip

## Download driver compiled 
cd /home/pi
** Version name will vary, replace with the one you downloaded **
wget https://github.com/audiophonics/I-Sabre_9038Q2M_Compiled/raw/master/I-Sabre_9038Q2M_4.14.84.zip
miniunzip I-Sabre_9038Q2M_4.14.84.zip

## Copy driver to Linux :
** Version name will vary, replace with your kernel version (uname -r) **
sudo cp i-sabre-codec.ko /lib/modules/4.14.84-v7+/kernel/sound/soc/codecs/
sudo cp i-sabre-q2m.ko /lib/modules/4.14.84-v7+/kernel/sound/soc/bcm/
sudo depmod -a
sudo cp i-sabre-q2m.dtbo /boot/overlays/

## Activate driver :
sudo nano /boot/config.txt

add :
dtoverlay=i-sabre-q2m
