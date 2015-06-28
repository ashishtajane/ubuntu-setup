ubuntu setup
============

Here, I am listing down things that I generally install on a fresh ubuntu installation for any future reference.


## Text Editors

#### Sublime Text 2
    sudo add-apt-repository ppa:webupd8team/sublime-text-2
    sudo apt-get update
    sudo apt-get install sublime-text

#### Atom
    sudo add-apt-repository ppa:webupd8team/atom
    sudo apt-get update
    sudo apt-get install atom

#### Eclipse

    # Download latest file
    tar -zxvf eclipse.XX.YY.tar.gz
    sudo mv eclipse.XX.YY /opt
    echo "[Desktop Entry]\nName=Eclipse\nType=Application\nExec=env UBUNTU_MENUPROXY=0 eclipse44\nTerminal=false\nIcon=eclipse\nComment=Integrated Development Environment\nNoDisplay=false\nCategories=Development;IDE;\nName[en]=Eclipse" > eclipse.desktop
    sudo desktop-file-install eclipse.desktop
    sudo ln -s /opt/eclipse/eclipse /usr/local/bin/eclipse44
    sudo cp /opt/eclipse/icon.xpm /usr/share/pixmaps/eclipse.xpm


## Shell

#### zshell and oh-my-zsh
    apt-get install zsh
    apt-get install git-core
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
    chsh -s `which zsh`


## Languages

#### Ruby and Rails
    sudo apt-get install build-essential make curl # prerequsites
    gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
    \curl -sSL https://get.rvm.io | bash -s stable
    source ~/.rvm/scripts/rvm
    rvm requirements
    rvm install ruby
    rvm use ruby --default
    rvm rubygems current
    echo "gem: --no-document" > ~/.gemrc
    gem install rails

#### NodeJS and NPM
    curl -sL https://deb.nodesource.com/setup | sudo bash -
    sudo apt-get install nodejs

#### Go
    wget https://storage.googleapis.com/golang/go1.4.2.linux-amd64.tar.gz
    sudo tar -C /usr/local -xzf go1.4.2.linux-amd64.tar.gz
    export PATH=$PATH:/usr/local/go/bin

#### Rust
    curl -sSf https://static.rust-lang.org/rustup.sh | sh

#### Java
    sudo apt-get install openjdk-7-jre
    sudo apt-get install openjdk-7-jdk


## Databases

#### MySQL
    sudo apt-get install mysql-server

#### Postgresql
    sudo apt-get update
    sudo apt-get install postgresql postgresql-contrib
    sudo -i -u postgres
    createuser -s -d -r -e ashish
    exit
    createdb ashish
    touch ~/.psql_history

#### MongoDB
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
    echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list
    sudo apt-get update
    sudo apt-get install mongodb-org


## Browsers

#### Google Chrome
    sudo apt-get install libxss1 libappindicator1 libindicator7
    wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
    sudo dpkg -i google-chrome-stable_current_amd64.deb


## Ubuntu Utilities

#### Synaptic Package Manager
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install synaptic

#### Grub Customizer
useful for multi-boot systems

    sudo add-apt-repository ppa:danielrichter2007/grub-customizer
    sudo apt-get update
    sudo apt-get install grub-customizer


## Communications

#### Skype
    sudo dpkg --add-architecture i386
    sudo apt-get update
    sudo apt-get install gdebi
    wget download.skype.com/linux/skype-ubuntu-precise_4.3.0.37-1_i386.deb
    sudo gdebi skype-ubuntu-precise_4.3.0.37-1_i386.deb


## File Sharing

#### Deluge
    sudo add-apt-repository ppa:deluge-team/ppa
    sudo apt-get update
    sudo apt-get install deluge


## Media

#### Clementine Music Player
    sudo add-apt-repository ppa:me-davidsansome/clementine
    sudo apt-get update
    sudo apt-get install clementine

#### VLC Media Player
    sudo apt-get install vlc


## Setup Git
Links - [Setup Git](https://help.github.com/articles/set-up-git/), [Generating SSH Keys](https://help.github.com/articles/generating-ssh-keys/)
    git config --global user.name "Firstname Lastname"
    git config --global user.email "username@email.com"
    if [ ! -d "~/.ssh" ]; then; mkdir ~/.ssh; fi
    # ls -al ~/.ssh
    ssh-keygen -t rsa -C "username@email.com" -N <passphrase> -f ~/.ssh/id_rsa
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_rsa # need passphrase here!
    sudo apt-get install xclip
    xclip -sel clip < ~/.ssh/id_rsa.pub
    # add ssh key to github
    # http://unix.stackexchange.com/questions/136894/command-line-method-or-programtically-add-ssh-key-to-github-com-user-account


## Misc Things

    sudo apt-get install aptitude

Flash Plugin

    sudo apt-get install flashplugin-installer

Video Codecs

    sudo apt-get install gstreamer0.10-plugins-ugly gxine libdvdread4 totem-mozilla icedax tagtool easytag id3tool lame nautilus-script-audio-convert libmad0 mpg321 gstreamer1.0-libav

Open terminal in arbitrary paths from nautilus UI

    sudo apt-get install nautilus-open-terminal

Compress software

    sudo apt-get install unrar-free p7zip-full

Tweaking unity

    sudo apt-get install unity-tweak-tool

Resetting unity

    unity-tweak-tool --reset-unity

API Testing

    sudo apt-get install httpie