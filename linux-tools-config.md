# Ubuntu 22.04.5

- su: passward
  - sudo passwd root
  
- proxy
  - echo $http_proxy
  - echo $https_proxy

- goko@debian:~/repo/share$ echo $http_proxy: goko is not in the sudoers file.
  - su -
  - usermod -aG sudo goko
  - exit 
  - exit 

- apt source(ubuntu 22.04)
  - cat /etc/apt/sources.list
deb http://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse

- apt source(debian 12.07)
  - sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
  - sudo bash -c 'cat > /etc/apt/sources.list << "EOF"
    deb http://mirrors.aliyun.com/debian/ bookworm main contrib non-free non-free-firmware
    deb-src http://mirrors.aliyun.com/debian/ bookworm main contrib non-free non-free-firmware
    deb http://mirrors.aliyun.com/debian-security bookworm-security main contrib non-free non-free-firmware
    deb-src http://mirrors.aliyun.com/debian-security bookworm-security main contrib non-free non-free-firmware
    deb http://mirrors.aliyun.com/debian/ bookworm-updates main contrib non-free non-free-firmware
    deb-src http://mirrors.aliyun.com/debian/ bookworm-updates main contrib non-free non-free-firmware
    deb http://mirrors.aliyun.com/debian/ bookworm-backports main contrib non-free non-free-firmware
    deb-src http://mirrors.aliyun.com/debian/ bookworm-backports main contrib non-free non-free-firmware
    EOF'

- wifi reinstall
  - sudo apt --fix-broken install 
  - sudo apt install --reinstall linux-firmware

- `ifconfig`
  - sudo apt install net-tools

- ~/.zshrc / .bashrc
  - export PATH="$HOME/.local/bin:$HOME/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"

- basic
  - sudo apt update && sudo apt upgrade -y
    - "when setting is not responding": sudo systemctl restart gdm (gnome)
  - sudo apt install gnome-tweaks tree git curl -y
  
- ssh
  - sudo apt install openssh-server -y 
  - sudo systemctl start ssh
  - sudo systemctl enable ssh

- Time
  - timedatectl (status)
  - sudo apt install ntpdate
  - sudo ntpdate time.windows.com

- Touchpad scroll
  - gsettings get org.gnome.desktop.peripherals.touchpad natural-scroll
  - traditional
    - gsettings set org.gnome.desktop.peripherals.touchpad natural-scroll false
  - fashion
    - gsettings set org.gnome.desktop.peripherals.touchpad natural-scroll true

- Terminal (NOW: echo $0)
  - sudo apt install zsh
  - chsh -s $(which zsh) (change shell to zsh)
  - sh -c "$(curl -fsSL https://install.ohmyz.sh/)"
  - git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    # gitee.com
      git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
  - ~/.zshrc: ZSH_THEME="powerlevel10k/powerlevel10k"
  - source ~/.zshrc
  - rebuild theme: p10k configure
  - zsh plugins
    - zsh-autosuggestions
      - git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
      - ~/.zshrc: plugins=(git zsh-autosuggestions)
      - source ~/.zshrc
    - zsh-syntax-highlighting
      - git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    - inline: z, extract, web-search
      - ......

- ssh-key
  - ssh-keygen -t rsa -b 4096 -C "goku.sonxin626@gmail.com"
    - 密-key: ~/.ssh/id_isa
    - pub-key: ~/.ssh/id_isa.pub : **add to github**
  - Add ssh into ssh-agent
    - eval "$(ssh-agent -s)" : "Starts ssh-agent and sets environment variables"
    - ssh-add ~/.ssh/id_rsa  : "Loads your private key into it"
      - **"ssh-agent" is a background program that manages your private keys, eliminating the need to re-enter your password each time you connect to GitHub.**
  - git check
    - ssh -T git@github.com
    - ssh -T git@gitlab.com
 
- neovim
  - download fonts.zip
  - unzip fonts.zip -d ~/.local/share/fonts
  - fc-cache -fv
  - sudo apt install -yqq python3 python3-venv python3-pip 
  - sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.10 1
    - Map the command `/usr/bin/python` to `python3.10`, so that executing `python` will use Python version 3.10 (for compatibility with some plugins).
  - export NVM_DIR=/root/.nvm
  - wget -q0 https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | zsh : **"download and run NVM-install-script, NVM:best to install the Node.js, also for neovim"**

- nextcloud
  - sudo add-apt-repository ppa:nextcloud-devs/client 
    - Add the officially maintained Nextcloud PPA to your system.This will get you the latest version of the Nextcloud desktop client (the built-in repository for Ubuntu is often outdated).
  - sudo apt update 
  - sudo apt install nextcloud-client 
  
- tailscale
  - curl -fsSL https://tailscale.com/install.sh | sh
 
- shallow clone: **Only download part of a git repo’s history to save time and space.**
  - clone after 2024-01-01
    - git clone --shallow-since=2024-01-01 https://git.onfoo.top/riscv/linux.git : Clone only commits after 2024-01-01.
    - git fetch --unshallow : Convert the shallow clone into a full clone.
  - add 1000 commit before 2024-01-01
    - git fetch --depth=1000 : Fetch 1000 more commits before the current history.
  - judge 
    - ls .git/shallow : have = good

- LFS <= 2G |||||| **normal: one max 100MB AND push max <= 2GB**
 - ex of .pdf
    - sudo apt install git-lfs
    - cd 你的项目
    - git lfs install : initialize Git LFS
    - git lfs track "*.pdf" : Tell Git LFS to track all .pdf files.
    - git add .gitattributes

    - git add books/*.pdf
    - git commit -m "Track PDFs with Git LFS"
    - git push origin main 

- tftp
  - sudo apt update
  - sudo apt install tftpd-hpa
  - config: /etc/default/tftpd-hpa
    - # /etc/default/tftpd-hpa
    - TFTP_USERNAME="tftp"
    - TFTP_DIRECTORY="/home/goko/repo/tftp"
    - TFTP_ADDRESS=":69"
    - TFTP_OPTIONS="-l -c -s" 
  - sudo chmod -R 777 /srv/tftp
  - sudo systemctl restart tftpd-hpa  
  - sudo ss -ulnp | grep :69

- riscv-toolchain 
  - sudo apt update
  - sudo apt install libncurses-dev libncursesw5-dev pkg-config
  - sudo apt install -y autoconf automake bison flex gawk gcc g++ libtool make \
                    patch python3-dev texinfo wget
  - sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev
  - sudo apt-get install make bison flex texinfo gawk
  - sudo apt-get install libncurses5-dev
  - sudo apt-get install libexpat1-dev
  - sudo apt-get install libgmp-dev libmpfr-dev libmpc-dev
  - sudo apt-get install libgmp-dev libmpfr-dev libmpc-dev
  - git clone --recursive https://github.com/riscv/riscv-gnu-toolchain
    - check: git submodule status
      - ex: gcc: 
        - cd gcc
        - git checkout master
        - git pull origin master
  - git submodule update --init gcc # in *toolchain
  - ./configure --prefix=$HOME/repo/gnu-bin --with-arch=rv64gc --with-abi=lp64 --enable-linux
  - sudo time make linux -j$(nproc)
  - ~/.zshrc:
    export ARCH="riscv"
    export CROSS_COMPILE="/repo/gnu-bin/bin/riscv64-unknown-linux-gnu-"
    export PATH="/repo/gnu-bin/bin:$PATH"  # 确保优先使用自编译工具链

- update git-repo 
  - 拉取远程最新的 main 分支覆盖本地 main 分支：⚠️ 注意：以下操作会丢弃本地 main 分支的修改
  git checkout main
  git fetch origin # Fetch latest commits from remote
  git reset --hard origin/main # Force local main to match remote
  git log --oneline --graph # View commit history briefly

- fusuma
  - sudo gpasswd -a $USER input
  - newgrp input
  - sudo apt-get install libinput-tools
    - sudo apt install aptitude
    - sudo aptitude install libinput-tools
    - sudo apt install libinput10=1.20.0-1ubuntu0.1 libinput-tools
  - sudo apt-get install ruby
  - sudo gem install fusuma
  - sudo apt-get install xdotool
  
- VMWARE 
git clone https://github.com/mkubecek/vmware-host-modules.git
cd vmware-host-modules 
git checkout workstation-16.2.5
sudo make
sudo make install
VMWARE 16.x
ZF3R0-FHED2-M80TY-8QYGC-NPKYF
Z1ZPR-EDGQN-M1JE9-HYFGX-YPGEX












------------------------------ **config-file:** -------------------------------
  - ~/.gitconfig
  - ~/.config/lei/config

~/.gitconfig
```bash
[core]
  editor = nvim
[user]
	name = Goko Son
	email = goku.sonxin626@gmail.com
[sendemail]
	smtppass = tciwjdbwyltanbkh
	smtpserver = smtp.gmail.com
	smtpuser = goku.sonxin626@gmail.com
	smtpencryption = tls
	smtpserverport = 587
	suppresscc = self
	chainreplyto = false
[filter "lfs"]
	required = true
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
[patatt]
	signingkey = ed25519:20250522
	selector = 20250522

[http]
	proxy = http://127.0.0.1:7897
[https]
	proxy = http://127.0.0.1:7897
```

























