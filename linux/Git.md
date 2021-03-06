# git学习笔记<!-- omit in toc -->

1. [配置编译环境](#配置编译环境)
    1. [下载源代码包](#下载源代码包)
    2. [安装依赖库文件](#安装依赖库文件)
2. [编译配置](#编译配置)
    1. [编译](#编译)
    2. [设置环境变量](#设置环境变量)
    3. [测试](#测试)

## 配置编译环境

### 下载源代码包

```shell
mkdir ~/src
cd ~/src
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.19.1.tar.gz
```

### 安装依赖库文件

```shell
yum install curl-devel expat-devel openssl-devel zlib-devel asciidoc
```

## 编译配置

### 编译

```shell
mkdir /opt/git
make prefix=/opt/git/ all
sudo make prefix=/opt/git/ install
echo $? # 查看是否编译安装完成
```

### 设置环境变量

```shell
mkdir /opt/bin
ln -s /opt/git/bin/* /opt/bin
echo "export PATH=$PATH:/opt/bin/" >> /etc/profile
source /etc/profile
```

### 测试

```shell
git --version

# 初始化
git config --global user.email "alex_zjf@163.com"
git config --global user.name "cc"
git config --global user.editor "vim"
```