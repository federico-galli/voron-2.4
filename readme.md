# Voron 2.4 
Klipper configuration for my Voron 2.4 `350*350*420` printer

## Setup
Classic Voron setup, running [klipper firmware](https://github.com/KevinOConnor/klipper) on a RaspberryPi4 connected via usb to two SKR 1.4 Turbo boards.

### Klipper and Octoprint
First [upgrade to Python3](https://octoprint.org/blog/2020/09/10/upgrade-to-py3/), then run the klipper dependencies installer, compile the firmware and flash it on the board. Install an octoprint plugin. 

Please refer to the [official documentation](https://www.klipper3d.org/Overview.html) for details.

### How to load klipper configuration
Check out this repository in /home/pi and add symlink to play nice with octoprint and klipper. Copy the extra udev to have auto-reconnect on phisical skr restart.

```bash
git clone https://github.com/federico-galli/voron-2.4.git ~/voron

ln -s voron/printer.cfg .
ln -s voron/config/ config

sudo cp voron/extras/98-klipper.rules /etc/udev/rules.d/
sudo systemctl restart udev
```