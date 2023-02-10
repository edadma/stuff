New Ubuntu setup instructions
=============================

First create another administrator user to do home folder encryption.

encrypted home folder
---------------------

1. ```
   sudo apt install ecryptfs-utils cryptsetup
   ```
2. You'll need to login to an admin account (user2) that's different from the user whose home directory you want to encrypt (user1).
3. ```
   sudo ecryptfs-migrate-home -u $USER
   ```

ubuntu packages
---------------

```
sudo apt install dolphin ark konsole tilix git default-jdk htop curl docker docker-compose hardinfo synaptic ansible sshpass net-tools openssh-server ccrypt nginx redis-server clang libgc-dev ffmpeg
```

docker group
------------

1. ```
   sudo usermod -aG docker $USER
   ```
2. restart is needed but perform next install (nvm) first

install node using nvm
----------------------

1. go to https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04
2. choose option 3
3. execute second curl command:
   ```
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
   ```
4. move lines that were appended to `.bashrc` to `.profile`
5. run
   ```
   source ~/.profile
   ```
6. run
   ```
   nvm install lts/gallium
   ```
7. check installation of `node`, `npm`, and `nvm` by typing
   ```
   node -v && npm -v && nvm -v
   ```
   
   you should see something close to
   ```
   v16.19.0
   8.19.3
   0.39.3
   ```
8. restart machine (needed for both nvm and docker group)

git config
----------

- ```
  git config --global user.email "you@example.com"
  ```
- ```
  git config --global user.name "Your Name"
  ```

slack
-----

download slack from https://slack.com/downloads/instructions/ubuntu

chrome
------

download chrome from https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

install sbt (for Scala JS or Scala Native development)
------------------------------------------------------

go to https://www.scala-sbt.org/download.html and follow Linux (deb) instructions:

1. ```
   echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
   ```
2. ```
   echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
   ```
3. ```
   curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
   ```
4. ```
   sudo apt-get update && sudo apt-get install sbt
   ```

install spotify
---------------

1. ```
   curl -sS https://download.spotify.com/debian/pubkey_7A3A762FAFD4A51F.gpg | sudo gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg
   ```
2. ```
   echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
   ```
3. ```
   sudo apt-get update && sudo apt-get install spotify-client
   ```

github token
------------

add github token to `~/.profile`:
```
export GITHUB_TOKEN="..."
```

ssh keys
--------

1. create using `ssh-keygen` or look in 1Password
2. ```
   chmod 700 ~/.ssh
   ```
3. ```
   chmod 600 ~/.ssh/*
   ```

jetbrains tools
---------------

1. ```
   sudo chown $USER:$USER /opt
   ```
2. download from https://www.jetbrains.com/toolbox-app/download/download-thanks.html?platform=linux
3. extract into `/opt/JetBrains/Toolbox` and run toolbox
4. set tools installation to `/opt/JetBrains` before starting any downloads
5. install Intellij, WebStorm, CLion, Android Studio

prettier (TypeScript formatting)
--------------------------------

1. ```
   npm install --global prettier
   ```
2. in WebStorm, go to Settings/Preferences -> Languages & Frameworks -> JavaScript -> Prettier
3. prettier should be installed at `~/.nvm/versions/node/v16.19.0/bin/prettier`

viber
-----

1. download https://download.cdn.viber.com/cdn/desktop/Linux/viber.deb

