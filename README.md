# NCS

### NCS安全客户端, 可压缩设备至NebulaChainSystem的连接数以及数据, 传输速度快, 且无法被中间人攻击及伪造请求攻击。

- linux安装
- open-wrt安装
- 如何使用？
- 连接池模式
- 更改默认网页访问端口?
- 设置NCS访问账号密码?
- 我想NCS一对多服务器如何使用？

请在下方寻找答案

# Linux安装

## 运行以下命令根据提示安装

#### 线路1（github官方地址, 如无法访问请使用其他线路）:

```sh
bash <(curl -s -L https://raw.githubusercontent.com/BernieMacMillan/NCS/main/install.sh)
```

#### 线路2:

```sh
bash <(curl -s -L -k https://mirror.ghproxy.com/https://raw.githubusercontent.com/BernieMacMillan/NCS/main/install.sh)
```

## OPEN-WRT安装

#### open-wrt输入以下命令进行安装

```
 wget -N https://mirror.ghproxy.com/https://raw.githubusercontent.com/BernieMacMillan/NCS/main/install.sh;chmod 777 install.sh;./install.sh
```
# WINDOWS安装

## 带有图形化界面的客户端

#### 下载地址

#### 线路1（github官方地址, 如无法访问请使用其他线路）:

```sh
https://github.com/BernieMacMillan/NCS/blob/main/windows-gui/ncs.exe
```

#### 线路2:(国内使用此线路)
```sh
https://mirror.ghproxy.com/https://github.com/BernieMacMillan/NCS/blob/main/windows-gui/ncs.exe
```

#### 图形化界面版本打开如果白屏闪退，请安装webview2, 下载地址

#### 线路1（github官方地址, 如无法访问请使用其他线路）:

```sh
https://github.com/BernieMacMillan/NCS/blob/main/windows-gui/MicrosoftEdgeWebview2Setup.exe
```

#### 线路2:(国内使用此线路)
```sh
https://mirror.ghproxy.com/https://github.com/BernieMacMillan/NCS/blob/main/windows-gui/MicrosoftEdgeWebview2Setup.exe
```

## 非图形化windows客户端（命令行）

#### 线路1（github官方地址, 如无法访问请使用其他线路）:
```sh
https://github.com/BernieMacMillan/NCS/blob/main/windows-no-gui/ncs.exe
```
#### 线路2:(国内使用此线路)
```sh
https://mirror.ghproxy.com/https://github.com/BernieMacMillan/NCS/blob/main/windows-no-gui/ncs.exe
```


# 如何使用?

安装完毕之后， 请在浏览器内访问安装NCS客户端设备地址，如 ip:42703，进入网页后填入推送地址即可。

安装NCS设备请尽量固定局域网IP，如果您的路由器是DHCP动态分配ip，则有可能安装设备重启后IP发生变化。


# 为什么windows图形界面版本打开白屏？

请安装windows-gui目录里的MicrosoftEdgeWebview2Setup.exe文件


# 连接池模式

NCS客户端设置菜单内，可以设置NCS至NebulaChainSystem的连接模式，如果选择连接池模式（需要NebulaChainSystem版本 >= 3.8.0）, 则开启公网连接数压缩（并非简单将矿机合并为一台，矿池内矿机数量不会发生变化），从NCS至NebulaChainSystem所在服务器的TCP连接数将被压缩。

以下为压缩率计算公式：
   
    压缩率 = 接入矿机数量 / 最大连接数

    压缩率不要太高, 最大连接数设置的越大，硬件负载越小
    通常3-5倍的压缩率即可, 根据NCS所在设备以及服务器硬件情况自行斟酌

    此处压缩的是NCS至服务器中间的公网tcp数量, 并非简单的矿机合并

# 如何更改默认网页访问端口?

手动修改目录下产生的NCS.conf文件, 里面有PORT配置项, 将此配置更改为需要的端口重启程序即可

# 如何设置NCS访问账号密码?

右上角设置内, 选择设置用户名密码即可

# 我想NCS一对多服务器如何使用？

NCS内提供手动添加, 选择手动添加按钮根据提示输入远程地址即可。