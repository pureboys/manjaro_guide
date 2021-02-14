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
9. yay -S iflyime   安装讯飞输入法

10. system settings -> language -> regional settings -> chinese
11. 输入法配置 

```
# edit .xprofile 如果没有就新建
export LC_ALL=zh_CN.UTF-8
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```
11.1 之后重启



12. sudo pacman -S mpv smplayer
13. sudo pacman -S code
14. sudo pacman -S google-chrome
15. sudo pacman -S shadowsocks-qt5
16. github 下载 SwitchyOmega, 配置安装
17. sudo pacman -S docker docker-compose

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
    "registry-mirrors": [
        "https://hub-mirror.c.163.com",
        "https://mirror.baidubce.com"
    ],
    "data-root": "/data/docker"
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
21. sudo pacman -S noto-fonts-emoji 
22. sudo pacman -S wps-office
23. sudo pacman -S ttf-wps-fonts
24. sudo pacman -S tmux
```
$ cd
$ git clone https://github.com/gpakosz/.tmux.git
$ ln -s -f .tmux/.tmux.conf
$ cp .tmux/.tmux.conf.local .
```

25. sudo pacman -S virtualbox
```
sudo gpasswd -a $USER vboxusers
# restart
```
26. sudo pacman -S vagrant 
27. sudo pacman -S flashplugin firefox-i18n-zh-cn
28. sudo pacman -S insomnia  # resful 请求
29. sudo pacman -S bleachbit # 清理垃圾
30. sudo pacman -S flameshot # 好用的截图工具

### 字体更改

```
sudo mkdir -p /usr/share/fonts/truetype/ttf-monaco && \
sudo wget https://gist.github.com/rogerleite/b50866eb7f7b5950da01ae8927c5bd61/raw/862b6c9437f534d5899e4e68d60f9bf22f356312/mfont.ttf -O - > \
/usr/share/fonts/truetype/ttf-monaco/Monaco_Linux.ttf && \
sudo fc-cache
```

