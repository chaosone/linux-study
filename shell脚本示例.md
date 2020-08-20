##指定一个目录,并判断是否存在并所属主是否属于当前用户
```
target="/usr/sbin/fdisk"
if [ ! -O $target ]         #judge if the target exists and it's owned by current user
then
    echo "you don't have permission to acess this file!!"
else
    ls -l $target
fi
```



##利用EOF写入多行文本
#!/bin/bash
cat>/etc/apt/sources.list<<EOF
deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib"
EOF


```
#!/bin/bash
echo "请确认以root用户身份执行!"
## 判断当前用户是否是root用户
if [ $(whoami) = "root" ];then
	echo "root用户！"
else
	echo "非root用户,请以root身份执行脚本!!"
fi

source="/etc/apt"
if [ ! -f "$source/sources.list.bak" ];then
    echo "备份源到/etc/apt/sources.list.bak"
    sleep 3
    cp $source/sources.list $source/sources.list.bak
else
    echo "备份文件已存在!!"
fi

cat>/etc/apt/sources.list<<EOF
deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
deb-src http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib"
EOF
```

## install wudao-dict
```
#!/bin/bash
echo "请先安装python3,和python3-pip"
cd $HOME
mkdir bin && cd bin
proxychains git clone https://github.com/chestnutheng/wudao-dict
cd ./wudao-dict/wudao-dict
sudo bash setup.sh
```
### echo mutli line
echo "first line
second line
3rd line."

### 测试sudo命令，切换用户执行命令
```
#!/bin/bash
sudo rmdir /usr/share/fonts/why
echo "current user is $(whoami)"
su - root
date        #这一句不会执行,具体原因还不清楚，总之在su - root后面的命令都不会执行
```
