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


## Shell

#### ZSH
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
