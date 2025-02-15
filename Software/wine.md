Doc:
https://wine.htmlvalidator.com/install-wine-on-debian-12.html
Doc Ufficiale:
https://gitlab.winehq.org/wine/wine/-/wikis/Debian-Ubuntu


sudo dpkg --add-architecture i386

sudo mkdir -pm755 /etc/apt/keyrings
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -


Add repository:


sudo apt update

NB
se durante l'update trovi questo errore:

kipping acquire of configured file 'main/binary-i386/Packages' as repository 'https://brave-browser-apt-release.s3.brave.com stable InRelease' doesn't support architecture 'i386

aggiungere il tag arch=amd64
Esempio:
deb [arch=amd64 signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main

Installare wine

sudo apt install --install-recommends winehq-stable



