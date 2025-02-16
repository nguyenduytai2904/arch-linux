# After installing arch linux

## Configure pacman
```bash
sudo nano /etc/pacman.conf
```
Uncomment Color to make the output colorful. If you want more fun, you can also add IloveCandy in the config file right after the color option.

## Install plocate to search faster than find
```bash
yay -S plocate
sudo updatedb
```
## Trim your SSD(SSD/NVMe)
```bash
sudo systemctl enable fstrim.timer
sudo systemctl start fstrim.timer
systemctl status fstrim.timer
```

##  Automatic cleaning the package cache
```bash
sudo pacman -S pacman-contrib
sudo systemctl enable paccache.timer
```
## Disable GRUB delay
```bash
sudo nano /etc/default/grub
```
Add set GRUB_TIMEOUT_STYLE=hidden
```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
## Enable TRIM for your SSD (SSD/NVMe)
```bash
sudo systemctl enable fstrim.timer
sudo systemctl start fstrim.timer
sudo systemctl status fstrim.timer
```
## Update your system
```
sudo pacman -Syu
```
## Install any AUR helper
```bash
sudo pacman -S git base-devel --needed
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
makepkg -si
```
## Power management

```bash
yay -S tlp
systemctl enable tlp.service
```

## Installing the second kernel in case the kernel boot error
- Linux LTS 
- Linux Hardened Kernel
- Linux Zen Kernel
```python
sudo pacman -S linux-lts linux-lts-headers
sudo grub-mkconfig -o /boot/grub/grub.cfg
reboot
```

## Install microcode
- for intel processors:
```bash
sudo pacman -S intel-ucode
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
- for AMD processors:
```bash
sudo pacman -S amd-ucode
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
## Install GUI packages managerment
```bash
sudo pacman -S pamac 
```

## Install plocate to search file fater than find 
```bash
yay -S plocate
updatedb
```


## Use Timeshift to backup system 
```bash
yay -Sy timeshift
systemctl enable cronie.service
systemctl start cronie.service
```

## Setup firewall
```bash
yay -S ufw
sudo systemctl enable ufw
sudo systemctl start ufw
```

## Install some tool essential
```bash
yay -S neofetch firefox chromium ...
```

## GPU Nvidia
```bash
yay -S dkms nvidia-dkms
mkinitcpio -P
reboot
```

## Enable Multilib repository

If you want to run 32-bit applications on your 64-bit system.
```bash
sudo nano /etc/pacman.conf
```
Uncomment:
```bash
[multilib]
include = /etc/pacman.d/mirrorlis
```
```bash
sudo pacman -Syu
```
