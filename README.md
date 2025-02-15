# After installing arch linux
## 1. Update your system
```
sudo pacman -Syu
```
## 2. Install any AUR helper
```bash
sudo pacman -S git base-devel --needed
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
makepkg -si
```
## 3. Power management

```bash
yay -S tlp
systemctl enable tlp.service
```

## 4. Installing the second kernel in case the kernel boot error
- Linux LTS 
- Linux Hardened Kernel
- Linux Zen Kernel
```python
sudo pacman -S linux-lts linux-lts-headers
```

## 5. Install microcode
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
## 6. Install GUI packages managerment
```bash
sudo pacman -S pamac 
```

## 7. Use Timeshift to backup system 
```bash
yay -Sy timeshift
systemctl enable cronie.service
systemctl start cronie.service
```

## 8. Setup firewall
```bash
yay -S ufw
sudo systemctl enable ufw
sudo systemctl start ufw
```

## 9. Install some tool essential
```bash
yay -S neofetch firefox chromium ...
```

## 10. GPU Nvidia
```bash
yay -S dkms nvidia-dkms
mkinitcpio -P
reboot
```
