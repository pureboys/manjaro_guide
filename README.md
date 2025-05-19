1. sudo pacman-mirrors -i -c China -m rank
2. sudo pacman -Syyu
3. sudo pacman -S vim yay
4. sudo pacman -S fcitx5 fcitx5-configtool fcitx5-qt fcitx5-gtk fcitx5-chinese-addons fcitx5-material-color kcm-fcitx5 fcitx5-lua
5.
```
#  ~/.xprofile

export INPUT_METHOD=fcitx
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
export SDL_IM_MODULE DEFAULT=fcitx

```
6. cp /usr/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart #自启动
7. 配置输入法皮肤  https://github.com/thep0y/fcitx5-themes

9. 修改英文目录
```
$ sudo pacman -S xdg-user-dirs-gtk
$ export LANG=en_US
$ xdg-user-dirs-gtk-update
$ #然后会有个窗口提示语言更改，更新名称即可
$ export LANG=zh_CN.UTF-8
$ #然后重启电脑如果提示语言更改，保留旧的名称即可
```

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
bip 调整网段用

sudo vim /etc/docker/daemon.json
{
    "registry-mirrors": [
        "https://hub-mirror.c.163.com",
        "https://mirror.baidubce.com"
    ],
    "data-root": "/data/docker",
    "bip": "192.168.100.1/24",
    "debug" : true,
    "default-address-pools" : [
        {
          "base" : "12.11.0.0/16",
          "size" : 24
        }
      ]
}

bip // 仅对docker可以用， docker-compose 不可以
default-address-pools // 可以对dock-compose 可以使用


systemctl enable docker
systemctl start docker

# docker-compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose


```

18. sudo pacman -S proxychains-ng

```
sudo vim /etc/proxychains.conf

```

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

31. 微信处理KDE 大小不一致问题

如果你的系统没有菜单编辑器，也可以自行将/usr/share/applications/wechat.desktop复制为~/.local/share/applications/wechat.desktop（菜单编辑器其实修改的也是家目录下的这个文件），然后编辑Exec=所在行，比如设置输入法为fcitx、设置自动缩放并添加x11支持：
`Exec=env QT_IM_MODULE=fcitx QT_AUTO_SCREEN_SCALE_FACTOR=1 'QT_QPA_PLATFORM=wayland;xcb' /usr/bin/wechat %U`



