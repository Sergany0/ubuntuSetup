sudo apt update && sudo apt upgrade -y

sudo apt remove --purge firefox
sudo snap remove --purge firefox


sudo add-apt-repository ppa:mozillateam/ppa

echo '
Package: *
Pin: release o=LP-PPA-mozillateam
Pin-Priority: 1001
' | sudo tee /etc/apt/preferences.d/firefox

OR

echo '
Package: firefox*
Pin: release o=LP-PPA-mozillateam
Pin-Priority: 501
' | sudo tee /etc/apt/preferences.d/firefox



echo '
Package: firefox*
Pin: release o=Ubuntu*
Pin-Priority: -1
' | sudo tee /etc/apt/preferences.d/firefox



echo 'Unattended-Upgrade::Allowed-Origins:: "LP-PPA-mozillateam:${distro_codename}";' | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox


sudo apt update
sudo apt install firefox
sudo apt install ubuntu-restricted-extras
gsettings set org.gnome.shell.extensions.dash-to-dock click-action minimize
sudo apt install gnome-software gnome-software-plugin-flatpak flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

sudo apt install chrome-gnome-shell gnome-shell-extension-prefs
sudo apt install gnome-tweaks gnome-shell-extension-manager

