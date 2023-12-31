nobara
https://nobaraproject.org/download-nobara/

powertools
https://github.com/hicder/PowerTools/releases

curl -L https://github.com/hicder/PowerTools/releases/download/v2.7/install.sh | sh

HANDYGCCS
sudo python -m pip install build wheel installer
git clone https://github.com/ShadowBlip/HandyGCCS.git
cd HandyGCCS
sudo ./build.sh

sudo nano /usr/lib/systemd/system/handycon.service

=============================================
[Unit]
Description=Handheld Game Console Controller Service
After=graphical-session.target

[Service]
Nice=-15
IOSchedulingClass=best-effort
IOSchedulingPriority=0
ExecStart=/usr/local/bin/handycon

[Install]
WantedBy=multi-user.target
=============================================
sudo systemctl enable --now handycon

DECKY LOADER

curl -L https://github.com/SteamDeckHomebrew/decky-installer/releases/latest/download/install_release.sh | sh

POWERTOOLS
sudo systemctl stop plugin_loader
rm $HOME/.config/powertools/limits_cache.json
sudo cp /tmp/backend $HOME/homebrew/plugins/PowerTools/bin/backend
sudo cp /tmp/index.js $HOME/homebrew/plugins/PowerTools/dist/index.js
sudo systemctl start plugin_loader

-------------------------------------
Commands:
Nobara Update hotfix:
sudo dnf update --exclude=nobara-login --refresh

Jlobue10 Tarball installation:
https://github.com/jlobue10/ALLY_Nobara_fixes/releases

cd /home/[username]/downloads
tar xvf kernel-6.5.12-201.fsync.ally.fc38.x86_64.tar.gz
cd RPM
sudo dnf install *.rpm

-----------------------------------
Steam-patch installation:
curl -L https://raw.githubusercontent.com/corando98/steam-patch/main/install.sh | sh

Power button fix:
sudo nano /etc/systemd/logind.conf.d/00-handheld-power.conf
under [Login] look for 'HandlePowerKey=ignore' and change to 'HandlePowerKey=suspend'
