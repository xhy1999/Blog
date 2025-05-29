# Ubuntu配置国内apt镜像

**环境**：
- Ubuntu24.04.2 LTS

**资源**：
- [华为开源镜像站](https://mirrors.huaweicloud.com/home)
- [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror/)

---

## (1).备份原有配置
```bash
sudo cp -a /etc/apt/sources.list.d/ubuntu.sources /etc/apt/sources.list.d/ubuntu.sources.bak
```

## (2).替换源地址(以清华源为例)
```bash
cd /etc/apt/sources.list.d
sudo vi ubuntu.sources
```
```vim
Types: deb
URIs: http://mirrors.tuna.tsinghua.edu.cn/ubuntu
Suites: noble noble-updates noble-backports noble-security
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
```

## (3).更新源缓存
```bash
sudo apt clean
sudo rm -rf /var/lib/apt/lists/*
sudo apt update
```

## (4).常用软件包
```bash
# SSH
sudo apt install ssh

# 编译环境
sudo apt install gcc
sudo apt install make

#unzip
sudo apt install unzip

# JAVA 8
sudo apt install openjdk-8-jdk
# 查看Java安装的目录
readlink -f $(which java) | sed "s:bin/java::"

# Nginx
sudo apt install nginx
```




