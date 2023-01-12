encrypted home folder
---------------------

1. sudo apt install ecryptfs-utils cryptsetup
2. You'll need to login to an admin account (user2) that's different from the user whose home directory you want to encrypt (user1).
3. sudo ecryptfs-migrate-home -u <user1>

ubuntu packages
---------------

dolphin ark konsole tilix git default-jdk htop curl docker docker-compose hardinfo synaptic ansible sshpass net-tools openssh-server ccrypt nginx redis-server clang libgc-dev

git config
----------

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

install sbt (for Scala JS or Scala Native development)
------------------------------------------------------

1. go to https://www.scala-sbt.org/download.html and follow Linux (deb) instructions

```
echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
sudo apt-get update
sudo apt-get install sbt
```

github token
------------

add github token to `~/.profile`

```
export GITHUB_TOKEN="..."
```

install node using nvm
----------------------

1. go to https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04
2. choose option 3
3. execute second curl command
4. move lines appended to `.bashrc` to `.profile`
5. run `source ~/.bashrc`
6. run `nvm install lts/gallium`
7. restart machine

jetbrains tools
---------------

1. type `sudo chown $USER:$USER /opt`
2. set tools installation to `/opt/JetBrains` before downloading
3. download https://download-cdn.jetbrains.com/toolbox/jetbrains-toolbox-1.27.2.13801.tar.gz to `/opt/JetBrains/Toolbox`
4. extract and run toolbox
5. install Intellij, WebStorm, CLion, Android Studio

prettier (TypeScript formatting)
--------------------------------

1. npm install --global prettier
2. in WebStorm, go to Settings/Preferences -> Languages & Frameworks -> JavaScript -> Prettier

viber
-----

1. download https://download.cdn.viber.com/cdn/desktop/Linux/viber.deb
