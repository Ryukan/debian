sudo dpkg --add-architecture i386 && sudo apt update
sudo apt install nvidia-driver-libs:i386

Add gpg
curl -s http://repo.steampowered.com/steam/archive/stable/steam.gpg | sudo tee /usr/share/keyrings/steam.gpg > /dev/null

Add repo
echo deb [arch=amd64,i386 signed-by=/usr/share/keyrings/steam.gpg] http://repo.steampowered.com/steam/ stable steam | sudo tee /etc/apt/sources.list.d/steam.list

Update
sudo apt update

Install - Ho skippato i driber mesa perche mi sava problemi alla vista
#sudo apt install libgl1-mesa-dri:amd64 libgl1-mesa-dri:i386 libgl1-mesa-glx:amd64 libgl1-mesa-glx:i386 steam steam-launcher -y
sudo apt install steam steam-launcher -y

Launche Stem
steam