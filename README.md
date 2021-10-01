1. sudo pacman-mirrors -i -c China -m rank
2. sudo pacman -Syyu
3. sudo pacman -S vim yay
4. sudo pacman -S fcitx5-rime fcitx5-configtool fcitx5-gtk fcitx5-qt
5.
```
#  ~/.pam_environment

GTK_IM_MODULE DEFAULT=fcitx
QT_IM_MODULE  DEFAULT=fcitx
XMODIFIERS    DEFAULT=\@im=fcitx
SDL_IM_MODULE DEFAULT=fcitx

```
6. cp /usr/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart #自启动
7. 配置输入法皮肤  https://github.com/thep0y/fcitx5-themes
8. 配置 rime 自定义词库
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
### rime 配置

```
cd /usr/share/rime-data
# 下载moegirl字典
wget https://github.com/outloudvi/mw2fcitx/releases/download/20210914/moegirl.dict.yaml
```
#### 配置自定义词库
```
# luna_pinyin_simp.custom.yaml 


patch:
# 指定自定义词库位置
  "translator/dictionary": oliver.extended
```

```
# oliver.extended.dict.yaml


# 原来要结合默认词库和第三方词库，
# 需要自己编写一个词库让它 fallback 到朙月拼音和第三方词库。
# 我说佛老师对不起对不起，我不懂规矩。
---
name: oliver.extended
version: "0.1"
# `by_weight`（按词频高低排序）或 `original`（保持原码表中的顺序）。
sort: by_weight
# 因为导入的朙月拼音词库是繁转简，所以这里不能导入简化字八股文。
# 导入简化字八股文。
# vocabulary: essay-zh-hans
# 选择是否导入预设词汇表【八股文】。
use_preset_vocabulary: true

import_tables:
  - luna_pinyin
  - moegirl

```


