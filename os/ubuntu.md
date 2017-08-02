# ubuntu远程桌面配置

1. 安装xfce4、xrdp、vnc4server，配置会话类型，重启rdp服务

    参考：http://www.linuxidc.com/Linux/2014-04/100491.htm
    ```
    sudo apt-get install xfce4
    sudo apt-get install xrdp vnc4server
    echo "xfce4-session" >~/.xsession
    sudo service xrdp restart
    ```

    使用dpkg -l 确认已经安装的包，如果已经安装，可以不用再重复安装
    参考：http://www.cnblogs.com/forward/archive/2012/01/10/2318483.html

    问题：安装后没有浏览器，安装firefox后，中文显示不对。

2. 完整安装ubuntu-desktop

    参考：http://www.cnblogs.com/platero/p/4123720.html
    ```
    sudo apt-get install xubuntu-desktop
    ```

# 遗留问题

1. 如何使用xdmcp登录ubuntu

    > https://wiki.ubuntu.com/xdmcp
    > 参考这个连接看是否能够搞定
 