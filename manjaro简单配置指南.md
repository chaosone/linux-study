## 1.修改pacman镜像源
[archlinuxcn]  
SigLevel = Never  
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch  
2.sudo pacman-mirrors -c China  
### ZSH config.

1. 安装zsh   

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"  

2. 安装oh-my-zsh   
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"  
zshrc的插件加载路径的默认文件夹是:  
~/.oh-my-zsh/custom/plugins  
## install nodejs npm packmanager
$ sudo pacman -S nodejs npm  
## install youtube-dl interactive
```npm install -g youtube-dl-interactive```

```
### some useful apps:
sudo pacman -S mplayer
sudo pacman -S fzf
sudo pacman -S neofetch
sudo pip3 install NetEase-MusicBox
sudo pip install ranger-fm
pip install thefuck
```
**note:when you are using pip, you should use sudo to get the root permission **
# install  ranger-fm
### 显示系统时间信息
```timedatectl status```
**arch更新显卡驱动：**   
$ sudo pacman -S xf86-video-intel intel-media-driver vulkan-intel xf86-video-amdgpu xf86-video-ati mesa-vdpau vulkan-radeon

### Arch安装Gnome:
```
$ sudo pacman -S xorg xorg-server xorg-xinit gnome gnome-extra
$ systemctl enable gdm
```

发现会有卡顿，将 Wayland 更改为 Xorg：
$ sudo vim /etc/gdm/custom.conf  
更改：
```
[daemon]
Uncoment the line below to force the login screen to use Xorg
-#WaylandEnable=false
+WaylandEnable=false
```
重启电脑,解决.

### 字体相关
更新字体缓存以生效（部分软件需重启软件才能生效）:  
$ fc-cache -fv  
fs-cache -fv  
