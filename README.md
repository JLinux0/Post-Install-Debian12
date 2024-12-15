# Post-Install-Debian12

## Configurações Básicas

1 - Atualize o Sistema
```
apt update ; apt upgrade -y
```
2 - Atualize o kernel do Linux
```
apt install linux-image-amd64 linux-headers-amd64 -t bookworm-backports
```

3 - Atualizando o firmware do seu processador
```
apt install intel-microcode
```

4 - Remova pacotes desnecessários, neste caso vamos remover os jogos e o pidgin, mas se vc usa estes aplicativos então pule esta etapa.
```
apt remove pidgin gnome-games --purge && apt autoremove
```

5 - Habilitando os botões de Maximizar e Minimizar
```
# Saia do Root para executar o comando!!!
gsettings set org.gnome.desktop.wm.preferences button-layout ':minimize,maximize,close'
```

6 - Configuração da sources.list 
```
nano /etc/apt/sources.list
```
```
deb http://deb.debian.org/debian/ bookworm main contrib non-free non-free-firmware
deb http://security.debian.org/debian-security bookworm-security main contrib non-free non-free-firmware
deb http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware
```

7 - Alterando o valor da swappiness
```
nano /etc/sysctl.conf
```
```
vm.swappiness=10
```

8 - Adicione seu usuário ao grupo sudo
```
apt install sudo
```
```
adduser seu_usuario sudo
```

9 - Instale os pacotes de fontes da Micro$oft
```
apt install ttf-mscorefonts-installer && fc-cache -f -v
```

10 - Ativando o firewall
```
apt install ufw gufw
```
```
ufw enable
```

11 - extração e compactação de arquivos
```
apt install arc arj cabextract lhasa p7zip p7zip-full p7zip-rar rar unrar unace unzip xz-utils zip
```

12 - Flatpak
```
apt install flatpak
```
```
apt install gnome-software-plugin-flatpak
```
```
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

13 - Removendo libreoffice e firefox-esr
```
apt remove libreoffice* ; apt remove firefox-esr*
```

14 - Gdebi
```
apt install gdebi
```

14 - Synaptic
```
apt install synaptic
```
