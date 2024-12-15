Doc:
https://www.if-not-true-then-false.com/2024/debian-vmware-install/

1 - Make VMware-Workstation-Full-17.6.0-24238078.bundle executable

chmod +x ~/Downloads/VMware-Workstation-Full-17.6.0-24238078.x86_64.bundle

2 - Change root user

sudo -i

3 - Install needed dependencies

apt install linux-headers-$(uname -r) gcc make patch wget pkexec

4 - Run Vmware Installer
./VMware-Workstation-Full-17.6.0-24238078.x86_64.bundle

5 - Build VMware Modules

/usr/bin/vmware-modconfig --console --install-all

