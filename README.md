# debian

## Nvidia Wayland
To enable kernel modesetting with the NVIDIA driver: 
# echo 'GRUB_CMDLINE_LINUX="$GRUB_CMDLINE_LINUX nvidia-drm.modeset=1"' > /etc/default/grub.d/nvidia-modeset.cfg
# update-grub

# systemctl enable nvidia-suspend.service
# systemctl enable nvidia-hibernate.service
# systemctl enable nvidia-resume.service

In addition, you will need to verify whether the PreserveVideoMemoryAllocations NVIDIA module parameter is turned on. Without the parameter being enabled, the udev rules in /usr/lib/udev/rules.d/61-gdm.rules will force a fallback to X11. To check the value of PreserveVideoMemoryAllocations: 
$ cat /proc/driver/nvidia/params | grep PreserveVideoMemoryAllocations
PreserveVideoMemoryAllocations: 1
# echo 'options nvidia NVreg_PreserveVideoMemoryAllocations=1' > /etc/modprobe.d/nvidia-power-management.conf

If not work.
sudo mv /usr/lib/udev/rules.d/61-gdm.rules /usr/lib/udev/rules.d/61-gdm.rules.bak

Firefox 
Add Apt source:
https://support.mozilla.org/en-US/kb/install-firefox-linux?utm_source=www.mozilla.org&utm_medium=referral&utm_campaign=firefox-download-thanks#w_install-firefox-deb-package-for-debian-based-distributions

Disable translation
Enter about:config in the address bar and set browser.translations.automaticallyPopup = false.

## Steam Wine Lutris
### Nvidia
enable 32-bit multiarch
sudo dpkg --add-architecture i386 && sudo apt update
sudo apt install nvidia-driver-libs:i386






