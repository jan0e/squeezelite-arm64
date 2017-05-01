# Squeezelite on arm64 running LibreELEC

This repo contains the binaries, retrieved from [packages.debian.org](https://www.debian.org/distrib/packages) needed to run Squeezelite on arm64 running LibreELEC.

##### Installation
1. Download and extract the files
```
cd /storage
wget https://github.com/jan0e/squeezelite-arm64/archive/master.zip
unzip master.zip
mv squeezelite-arm64-master/ squeezelite-arm64
rm master.zip
```

2. Run Squeezelite on every reboot
```
cd /storage/.config
nano autostart.sh
```
Add the following:
```
(
 export LD_LIBRARY_PATH=$LD_LIBARY_PATH:/storage/squeezelite-arm64/lib
 /storage/squeezelite-arm64/bin/squeezelite -a 160:::0 -C 1 -n $(hostname)
) &
```
Press CTRL+o to save and CTRL+x to quit the text editor. Reboot LibreELEC and you should see the hostname available as player in Logitech Media Server.
