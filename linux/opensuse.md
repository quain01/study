# OpenSUSE硬盘安装

参考：[SDB:硬盘安装方式](https://zh.opensuse.org/index.php?title=SDB:%E7%A1%AC%E7%9B%98%E5%AE%89%E8%A3%85%E6%96%B9%E5%BC%8F&variant=zh-cn)

1. 把opensuse iso文件放置到某个目录下，并把linux、initrd文件提取出来

```
    openSUSE.iso/boot/x86_64/loader/linux
    openSUSE.iso/boot/x86_64/loader/initrd
```

2. 准备grub的配置文件，增加一个启动项，从光盘中的kernel、initrd引导启动

    说明：下面root中的(hdX,Y)即是存放iso镜像所在的硬盘分区，kernel、initrd中的(hdX,Y)可以不写，后面跟着的即是该分区中linux、initrd的路径。

```
    title openSUSE Install
        root (hdX,Y)
        kernel (hdX,Y)/linux
        initrd (hdX,Y)/initrd
```

3. 重启服务器，引导进入OS安装过程，完成OS安装。

4. 配置suse远程桌面：启动DM的远程访问、Root登录，开启防火墙端口，正常使用。

```
    Open a terminal as root
    Launch: yast2
    Click on: System > /etc/sysconfig Editor
    Desktop > Display manager > DISPLAY_MANAGER_REMOTE_ACCESS > yes
    Desktop > Display manager > DISPLAY_MANAGER_ROOT_LOGIN_REMOTE > yes
    Firewall > SuSEfirewall2 > FW_SERVICES_EXT_UDP > 177
    Click Finish
```
