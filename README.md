# Bemellah Mac

A comprehensive package designed to seamlessly initialize and configure your new Mac. With a simple command, equip your
macOS with essential tools and settings to enhance productivity and streamline your setup process.

- [ ] Remove unusable application from Dock bar
- [ ] Preferences -> Dock & menu Bar -> enable "Magnification" and reduce zoom of "Magnification" - enable "Authmaticlly
  hide and show the Dock"
- [ ] Preferences -> Track Pad -> enable "Tab to click"
- [ ] Right click desktop -> enable "Use Stacks"
- [ ] Finder Preferences
    - [ ] General -> select "mont" inside of "New finder windows show:"
    - [ ] Sidebar -> enable "mont" inside of "Shows these items in sidebar"
- [ ] Finder top bar
    - [ ] View -> Show path bar
- [ ] Finder cmd+j -> Sort by name -> At the end of window -> Use set as Defaults

## Developer directory

### Main directories

```{r, engine='bash', count_lines}
mkdir ~/Developer ~/Developer/Projects ~/Developer/Tools ~/Developer/IDEs
```

### IDEs directories

```{r, engine='bash', count_lines}
mkdir ~/Developer/IDEs/PHPStorm ~/Developer/IDEs/WebSorm ~/Developer/IDEs/Goland ~/Developer/IDEs/DataGrip ~/Developer/IDEs/CLion ~/Developer/IDEs/PyCharm ~/Developer/IDEs/DataSpell
```

## Using Touch id in Terminal

```{r, engine='bash', count_lines}
sudo nano /etc/pam.d/sudo
```

then insert next line in line number

```
auth       sufficient     pam_tid.so
```

## ZSH

```{r, engine='bash', count_lines}
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Add some plugins

```{r, engine='bash', count_lines}
nano ~/.zshrc
```

then replace **plugins=(git)** by **plugins=(git docker docker-compose kubectl oc helm yarn zsh-autosuggestions)**

## Aliases

add to end of ~/.zshrc

```
if [ -f ~/.bash_aliases ]; then
. ~/.bash_aliases
fi

if [ -f ~/.bash_profile ]; then
. ~/.bash_profile  
fi
```

Run this in your terminal

```{r, engine='bash', count_lines}
cp ./TerminalFiles/bash_profile.txt ~/.bash_profile
cp ./TerminalFiles/bash_aliases.txt ~/.bash_aliases
```

# Brew

```{r, engine='bash', count_lines}
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install php go node yarn cocoapods htop nginx k6 helm nats-server mysql redis jq youtube-dl openfortivpn openconnect
brew services restart nginx
brew services restart nats-server
brew services restart redis
brew services restart mysql
```

# SSH Key

```{r, engine='bash', count_lines}
ssh-keygen -t ed25519 -C "<ssh-keygen-name>"
cat ~/.ssh/id_ed25519.pub
```

# PHP & Laravel

```{r, engine='bash', count_lines}
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
mv composer.phar /usr/local/bin/composer
composer global require laravel/installer
composer global require laravel/valet
valet install
```

# Install Applications

- [ ] install [Chrome](https://www.google.com/chrome/)
- [ ] install [Firefox](https://www.mozilla.org/en-GB/firefox/download/thanks/)
- [ ] install [Folx](https://soft98.ir/mac/download-manager-mac/1005-folx.html)
- [ ] install [VSCode](https://code.visualstudio.com/download)
- [ ] install [Postman](https://www.postman.com/downloads/)
- [ ] install [VLC](https://www.videolan.org/vlc/download-windows.html)
- [ ] install Openvpn
- [ ] install Cloudflare WRAP
- [ ] install [Skype](https://www.skype.com/en/get-skype/)
- [ ] install [Telegram](https://apps.apple.com/us/app/telegram/id747648890?mt=12)
- [ ] install [Whatsapp](https://apps.apple.com/us/app/whatsapp-desktop/id1147396723?mt=12)
- [ ] install [Unarchiver](https://apps.apple.com/us/app/the-unarchiver/id425424353?mt=12)
- [ ] install [Persian Calendar](https://apps.apple.com/us/app/rouzshomar/id476295182?mt=12)
- [ ] install [SpeedTest](https://apps.apple.com/us/app/speedtest-by-ookla/id1153157709?mt=12)
- [ ] install Android Studio
- [ ] install [Xcode](https://apps.apple.com/us/app/xcode/id497799835?mt=12)
- [ ] install [Paste](https://soft98.ir/mac/desktop-tools-mac/3156-paste-mac.html)

# Jetbrains

```
cp -R ./Jetbrains/ja-netfilter ~/Developer/Tools/
sh ~/Developer/Tools/ja-netfilter/scripts/install.sh
```

COPY Activation code from https://dl2.soft98.ir/programing/2021-2022_Code.html

- [ ] Import Jetbrains IDE settings from ./Jetbrains
