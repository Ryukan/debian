# Envycontrol

Doc: https://github.com/bayasdev/envycontrol

## Install

Go to the latest release page (https://github.com/bayasdev/envycontrol/releases/latest)
Download the attached python3-envycontrol_version.deb package
Install it with sudo apt -y install ./python3-envycontrol_version.deb
Run sudo envycontrol -s <MODE> to switch graphics modes

## Usage 

usage: envycontrol.py [-h] [-v] [-q] [-s MODE] [--dm DISPLAY_MANAGER] [--force-comp] [--coolbits [VALUE]] [--rtd3 [VALUE]] [--reset-sddm] [--reset] [--verbose]

options:
  -h, --help            show this help message and exit
  -v, --version         Output the current version
  -q, --query           Query the current graphics mode
  -s MODE, --switch MODE
                        Switch the graphics mode. Available choices: integrated, hybrid, nvidia
  --dm DISPLAY_MANAGER  Manually specify your Display Manager for Nvidia mode. Available choices: gdm, gdm3, sddm, lightdm
  --force-comp          Enable ForceCompositionPipeline on Nvidia mode
  --coolbits [VALUE]    Enable Coolbits on Nvidia mode. Default if specified: 28
  --rtd3 [VALUE]        Setup PCI-Express Runtime D3 (RTD3) Power Management on Hybrid mode. Available choices: 0, 1, 2, 3. Default if specified: 2
  --use-nvidia-current  Use nvidia-current instead of nvidia for kernel modules
  --reset-sddm          Restore default Xsetup file
  --reset               Revert changes made by EnvyControl
  --cache-create        Create cache used by EnvyControl; only works in hybrid mode
  --cache-delete        Delete cache created by EnvyControl
  --cache-query         Show cache created by EnvyControl
  --verbose             Enable verbose mode

Example

sudo envycontrol -s integrated
sudo envycontrol -s nvidia 
envycontrol --query
