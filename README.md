1. sudo pacman-mirrors -i -c China -m rank
2. sudo pacman -Syyu
3. sudo pacman -S vim
4. sudo vim /etc/pacman.conf

```
[archlinuxcn]
SigLevel = Optional TrustedOnly
Server = http://mirrors.163.com/archlinux-cn/$arch
```

5. sudo pacman -Sy archlinuxcn-keyring
6. sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
7. sudo pacman -S fcitx-im
8. sudo pacman -S fcitx-configtool
9. sudo pacman -S fcitx-sogoupinyin

10. system settings -> language -> regional settings -> chinese
11. 输入法配置 -> sogou pinyin


```
# edit .zshrc
export LC_ALL=zh_CN.UTF-8
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```
12. sudo pacman -S mpv
13. sudo pacman -S code
14. sudo pacman -S google-chrome
15. sudo pacman -S shadowsocks-qt5
16. github 下载 SwitchyOmega, 配置安装
17. sudo pacman -S docker

```
Docker 官方中国区
https://registry.docker-cn.com

网易
http://hub-mirror.c.163.com

ustc
https://docker.mirrors.ustc.edu.cn


sudo usermod -aG docker $USER


sudo vim /etc/docker/daemon.json
{
  "registry-mirrors": ["https://registry.docker-cn.com"]
}

systemctl enable docker
systemctl start docker

# docker-compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose


```

18. sudo pacman -S proxychains-ng

```
sudo vim /etc/proxychains.conf

```

19. sudo pacman -S go
20. sudo pacman -S goland goland-jre
