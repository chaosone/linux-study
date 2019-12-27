>terminal 是终端仿真器应用程序 比如iterm  
shell 是linux与系统交互的一个程序  比如fish,bash,zsh  

- **rwx权限解释:**  
对于文件   				r read			w edit 				x  execute
对于文件夹 				r 读取目录内容 		w  				x


#### axel args:
-a 	显示简单进度条,一般带上好点  
-o /path/filename		指定文件名,如果不带filename,则存为默认文件名(网站上的文件名)  
-n 10								指定下载线程为10  
  
-----  
- **wget参数**   
-b					后台下载  
-c 				继续执行上次的任务  
-i url.txt	从url.txt获取下载链接  
-nc	如果指定目录存在文件,则不下载  
-O 	下载并以指定文件名保存  
-o      保存下载信息到指定文件而不是标准输出.				例:wget -o download.log DOWNLOAD-URL  
--limit-rate=400k	限制  


```wget -r -A.pdf http://url-to-webpage-with-pdfs/	  -A参数表示只下载pdf格式的文件  ```



===========================================================================  




进程管理:
显示进程
结束进程
显示占用端口


========================================================================================
## 更改系统时间:
在linux中计算机有两个时钟,一个是硬件时钟(real time clock),一个是系统时钟(system clock)  
硬件时钟通过BIOS电池运行,系统时钟通过cpu tick运行,默认情况下系统时间不会和硬件时间同步  
查看时间:  
系统时间可以通过date命令查询  
硬件时钟需要使用sudo hwclock 命令查询  
- 设置系统时间:  
date -s "2017-07-11 14:29:22"  
- 设置硬件时钟:  
hwclock --set --date="2017-07-11 14:29:22"  
- 把系统时间设置成硬件时间:  
hwclock --systohc  
- 把硬件时间设置成系统时间:  
hwclock --hctosys  
=========================================================================================


** crontab文件的含义：**  
用户所建立的crontab文件中，每一行都代表一项任务，每行的每个字段代表一项设置，它的格式共分为六个字段，前五段是时间设定段，第六段是要执行的命令段，格式如下：

minute   hour   day   month   week   command     顺序：分 时 日 月 周
其中：

minute： 表示分钟，可以是从0到59之间的任何整数。  
hour：表示小时，可以是从0到23之间的任何整数。  
day：表示日期，可以是从1到31之间的任何整数。  
month：表示月份，可以是从1到12之间的任何整数。  
week：表示星期几，可以是从0到7之间的任何整数，这里的0或7代表星期日。  
command：要执行的命令，可以是系统命令，也可以是自己编写的脚本文件。  

** example ** <++>:



tmux prefix+z				调整当前面板为全屏/非全屏

musicbox快捷键:
,										like(添加到我喜欢的音乐)


## pacman部分用法
- 同步并且更新你的系统
  sudo pacman -Syyu
- 在软件仓库中搜索软件
  sudo pacman -Ss [software package name]
- 查看已安装软件
```bash
sudo pacman -Qs [software package name]  
sudo pacman -Qi [software package name] # 附带详细信息  
sudo pacman -Qii [software package name] # 附带更加详细的包信息  
```
sudo pacman -Ql # 列出所有安装的软件包  
2.4 查看软件的详细依赖  
sudo pactree [software package name]
2.5 查看系统中那些没有被使用软件依赖包（orphans）  
sudo pacman -Qdt  
2.6 自动移除那些系统中没有被使用的依赖包【类似于Debian下的 sudo apt autoremove --purge】  
sudo pacman -Rs $(pacman -Qdtq)  
2.7 下载并安装软件包  
sudo pacman -Syu [software package name] #从软件仓库安装  
yay -S [software package name]  # Packages from the AUR  
- 从本地安装:  
sudo pacman -U [/package_path/][software package name.pkg.tar.xz] # 从本地安装
- 从网络安装(not offical reposity):  
pacman -U http://www.examplepackage/repo/examplepkg.tar.xz # 从网络安装【非官方仓库】

2.8 卸载软件  
sudo pacman -R [software package name] 
sudo pacman -Rs [software package name] # 同时删除依赖  
sudo pacman -Rns [software package name] # 删除软件及其依赖，还有pacman生成的配置文件，即更彻底的删除  
2.9 清空缓存(默认情况下安装软件会先来缓存中查看是否已经下载过，没有再去下载，软件安装后通常下载缓存还在)  
sudo pacman -Sc  
sudo pacman -Scc # 更彻底的清理  
关于 pacman 常用就这些了，更多请使用 man pacman OR pacman -h 去查看
- 解压tar.xz文件：
 xz -d xxx.tar.xz 将 xxx.tar.xz解压成 xxx.tar 然后，再用 tar xvf xxx.tar来解包。
yag=yagmail.SMTP()
========================================================================================
## ssr一键安装脚本:
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh

=======================================================================================

**ssh连接远程主机:**  
ssh user@xxx.xxx.xxx.xxx  
**scp命令**   
scp -r user@remoteip:remotefolder localfolder		#从远程服务器拷贝到本地  
scp local_file remote_ip:remote_file        #从本地拷贝到远程服务器  


查看文件 
指定打开方式
多选(复制,剪切,移到回收站,)
新建文件夹,文件



安装shadowsocks图形界面客户端:
sudo pacman -S shadowsocks-qt5


PORT:23797
UUID:3479af10-357c-4c41-85b2-fbe47828e30b


git config --global user.name "your name"（代表github用户名）

git config --global user.email "your_email@youremail.com"（github邮箱）

切换成

scp [参数] [原路径] [目标路径]

安装v2ray过程:
首先下载脚本
wget https://install.direct/go.sh
执行安装脚本
sudo bash go.sh

3.当出现类似下面的字样就算是安装成功了
PORT:40827
UUID:505f001d-4aa8-4519-9c54-6b65749ee3fb
Created symlink from /etc/systemd/system/multi-user.target.wants/v2ray.service to /lib/systemd/system/v2ray.service.
V2Ray v2.33 is installed.

4.校准时区


5.服务器端使用同样的配置(需要几下port,uuid以用来配置v2ray)



=============================================
linux下passwd文件结构:
用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录Shell

==========================
- arch安装fcitx输入法
```
sudo pacman -S fcitx-im
sudo pacman -S fcitx-configtool
sudo pacman -S fcitx-sougoupinyin
sudo pacman -S fcitx-sogoupinyin
sudo pacman -S fcitx-sogoupinyin
```

sudo pacman -S archlinux-keyring					
https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt

**查看某个端口是否被占用**
lsof -i:1080

ssr http proxy settings:
export http_proxy="http://127.0.0.1:12333"
export https_proxy="http://127.0.0.1:12333"

sudo mkfs.ntfs -f /dev/sdc1		
-f表示快速格式化 perform a quick form file  
sudo mkfs.ext4 -T largefile /dev/sdb1  		
###遇到问题先仔细看看man或者 -h 里面选项都有说明,通常这都比google来的快
fdisk  /dev/sdc1 			#指定磁盘进行磁盘操作  
m 											#查看指令菜单  
n 											#新建一个分区  
d 											#删除一个分区  
每个块磁盘至少主分区(primary),必须有1个,扩展分区(extend)0-3个,逻辑分区可以有0-n个.  

youtube-dl -r 300k				#限制下载速度为300k  
youtube-dl --proxy socks5://127.0.0.1   
scp root@136.244.109.14:/root/ssr.sh ~/music 			#从远程主机拷贝文件到本地  
scp ~/doc/shell学习笔记 @root@136.244.109.14:/root/     #从本地复制到远程服务器  

ln命令
硬链接：
ln 原文件 目标链接path

**some bold text** and some *italic text*   
### [baidu](http://www.baidu.com) 

sudo dd if=/dev/sdc1 /run/media/why/新加卷/chipfancer-disk/1.zip bs=1M

### 格式化某个分区 -f参数是快速格式化  
sudo mkfs.ntfs -f /dev/sdc1  

## dd命令用法  
#### 备份MBR内容  
dd if=/dev/sda of=mbr bs=512 count=1  
#### 将文件中所有小写字母转换成大写字母，并输出到标准输出  

#### dd把文件内的所有小写字母转换成大写  
dd if=file.txt status=none conv=ucase  

#### 复制某个分区到某个目录
sudo dd if=/dev/sdc1 /run/media/why/新加卷/chipfancer-disk/1.zip bs=1M 	 

#### vim配置：
vnoremap Y "+y 		#可视模式下复制到系统剪贴板

### 调整zsh光标,写入模式为'|',普通模式是方块
#function zle-line-init zle-keymap-select {
```
	#RPS1="${${KEYMAP/vicmd/-- NOR --}/(main|viins)/-- INS --}"
	#RPS2=$RPS1
	#zle reset-prompt
#}

function zle-keymap-select {
	if [[ ${KEYMAP} == vicmd ]] || [[ $1 = 'block' ]]; then
		echo -ne '\e[1 q'
	elif [[ ${KEYMAP} == main ]] || [[ ${KEYMAP} == viins ]] || [[ ${KEYMAP} = '' ]] || [[ $1 = 'beam' ]]; then
		echo -ne '\e[5 q'
  fi
}
zle -N zle-keymap-select

# Use beam shape cursor on startup.
echo -ne '\e[5 q'

# Use beam shape cursor for each new prompt.
preexec() {
	echo -ne '\e[5 q'
}

_fix_cursor() {
	echo -ne '\e[5 q'
}
precmd_functions+=(_fix_cursor)


zle -N zle-line-init
zle -N zle-keymap-select

KEYTIMEOUT=1
```
