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
  - sudo apt install gnome-tweaks tree git(~/.gitconfig) curl -y        ----------down----------
  
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

- mutt and lei : lei download email -> Mutt read and replay email -> git send-email send-email
  - lei:
    - sudo apt update
    - sudo apt install -y \
      vim wget curl git build-essential pkg-config \
      libgit2-dev xapian-tools \
      libinline-c-perl libany-uri-escape-perl \
      libdbd-sqlite3-perl libsearch-xapian-perl \
      libmail-imapclient-perl libplack-middleware-reverseproxy-perl \
      libcrypt-cbc-perl liblinux-inotify2-perl
    - wget https://public-inbox.org/public-inbox.git/snapshot/public-inbox-1.9.0.tar.gz
    - tar zxvf public-inbox-1.9.0.tar.gz && cd public-inbox-1.9.0
    - perl Makefile.PL INSTALLDIRS=vendor
    - make -j$(nproc)
    - sudo make install

  - Mutt:
    - sudo apt install mutt
    - touch ~/.muttrc : ----------down----------
    - config proxy:
      - sudo apt install proxychains4 
      - sudo nvim /etc/proxychains4.conf
        - change "socks4 	127.0.0.1 9050" to "socks5 	127.0.0.1 7897"
    - -f: open specify dir to read
  - example:
    - lei q -o ~/Mail/CTF2301/ --threads -I https://lore.kernel.org/all s:"hwmon" f:"Guenter" t:"troy"
    - lei q -o ~/Mail/linux-i2s --threads -I https://lore.kernel.org/all s:"ASoC: spacemit: add i2s support for K1 SoC" f:"troy"

- PLCT-nextcloud
  - alias mysync="nextcloudcmd -s --user 'GoKo-Son626' --password 'riscv0315!' ${HOME}/nextcloud/rvlk-cloud https://rvlk.onfoo.top/nextcloud"

- STM32f103zet6 env: ubuntu 22.04 + ST-Link/V2 仿真器(烧录到SMT8/32的Flash中)
  - sudo apt update
  - sudo apt install gcc-arm-none-eabi gdb-multiarch make # 交叉编译器 调试器 构建工具 
  - sudo apt install openocd # 烧录/调试软件
  - OK -> github:GoKo-Son626:ubuntu-STM32F103

- STM32CubeMX:
  - The official website download .zip and unzip 
  - sudo apt update
  - sudo apt install default-jre 
  - unzip stm32cubemx-lin-v6-15-0.zip
  - chmod +x SetupSTM32CubeMX-6.15.0
  - ./SetupSTM32CubeMX-6.15.0


------------------------------ **config-file:** -------------------------------
  - ~/.gitconfig
  - ~/.config/lei/config
  - ~/.muttrc

~/.gitconfig
```bash
[core]
  editor = nvim
[user]
	name = Goko Son
	email = goku.sonxin626@gmail.com
[sendemail]
	smtppass = 
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

~/.config/lei/config
```bash 
[leistore]
        dir = /home/goko/.local/share/lei/store
```

~/.muttrc
```bash 
# MAP ====================
set imap_user = goku.sonxin626@gmail.com
set imap_pass = odljwxogkpvuxdnx

set spoolfile = imaps://imap.gmail.com/INBOX
set folder = imaps://imap.gmail.com/
set record="imaps://imap.gmail.com/[Gmail]/Sent Mail"
set postponed="imaps://imap.gmail.com/[Gmail]/Drafts"
set mbox="imaps://imap.gmail.com/[Gmail]/All Mail"
set header_cache = "~/.mutt/cache/headers"
set message_cachedir = "~/.mutt/cache/bodies"
set certificate_file = "~/.mutt/certificates"`

# ================  Composition  ====================
set editor = "nvim"      # Set your favourite editor.
set edit_headers = yes  # See the headers when editing
set charset = UTF-8     # value of $LANG; also fallback for send_charset

# ================  MSMTP ====================
# I use msmtp to send. It depends on you.
set sendmail = "/usr/bin/msmtp"
set realname = "Goko Son"
set from = "goku.sonxin626@gmail.com"
set use_from = "yes"
set envelope_from = "yes"

# ================  SMTP  ====================
#set smtp_url = "smtp://goku.sonxin626@smtp.gmail.com:587/"
#set smtp_pass = $imap_pass
#set ssl_force_tls = yes # Require encrypted connection

# Status Bar -----------------------------------------
set status_chars  = " *%A"
set status_format = "───[ Folder: %f ]───[%r%m messages%?n? (%n new)?%?d? (%d to delete)?%?t? (%t tagged)? ]───%>─%?p?( %p postponed )?───"

# sort--------------
set sort = threads
set sort_aux = reverse-last-date-received

# bind------
bind index g group-chat-reply

# 让 pager 里 j/k 正常上下移动
bind pager j next-line
bind pager k previous-line

# 在 pager 界面，- 和 = 控制上一封/下一封邮件
bind pager - previous-entry
bind pager = next-entry

# 把 <Backspace> 映射为 previous-page
bind pager <Backspace> previous-page

# config---
# 每次发送邮件时将自己加入 CC 字段
set metoo=yes
my_hdr Cc: "Goko Son" <goku.sonxin626@gmail.com>

# use nvim to read email
set pager="nvim -"

# check email every 60s
set mail_check=60

auto_view text/html
alternative_order text/plain text/enriched text/html

ignore *
unignore From: Date: To: Cc: Subject: Reply-To: List-ID: Message-ID: In-Reply-To:
hdr_order From: Date: To: Cc: Subject: Reply-To: List-ID: Message-ID: In-Reply-To:
```


