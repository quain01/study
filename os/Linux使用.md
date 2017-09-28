# 选择：
1. 如何选择发行版
2. 如何选择桌面环境

# 使用：
1. 虚拟机 or 物理机
2. 如何安装

# 桌面环境参考如下内容：
1. https://linux.cn/article-7081-1.html
2. https://linux.cn/article-6021-1.html
3. https://www.zhihu.com/question/29098445

选择KDE 5

发行版选择CentOS，服务器OS应该比较稳定。

虚拟化软件使用什么：Windows上可以使用VMware Player和Virtual Box，选择Virtual Box。

# 配置过程：
1. 下载virturl box，并安装
2. 下载CentOS 7.3 ISO镜像
3. 创建虚拟机，使用CentOS 7.3 ISO引导，完成安装
4. 配置输入法为ibus 智能拼音输入法
   可能碰到的问题：桌面环境安装不全，导致配置失败
   解决方案：可以使用yum grouplist查找到桌面环境的group包，使用yum groupinstall重新安装，即可解决该问题
5. 修改系统字体设置为wenquanyi
6. 修改firefox的字体设置为wenquanyi
   碰到的问题：firefox的所有页面都无法打开，删除系统的firefox，从网上下载最新版本并安装解决了问题
7. 下载XX，unzip，./start，开启浏览器，下载证书

# 字体知识：
- wenquanyi zen hei 文泉驿正黑
- wenquanyi zen hei mono 文泉驿等宽正黑
- wenquanyi zen hei sharp 文泉驿点阵正黑
- wenquanyi micro hei 文泉驿微米黑
- wenquanyi micro hei mono 文泉驿等宽微米黑

# yum命令：
1. yum grouplist：查看可用的软件组
2. yum groupinfo：查看软件组信息
3. yum groupinstall：安装一组软件
4. yum clean all：修改安装源配置后，使用本命令清楚本地缓存信息
5. yum makecache：修改安装源配置后，使用该命令刷新本地缓存

# 远程登录：
1. xrdp：使用windows mstsc登录。ubuntu下安装xrdp服务，配置登录桌面为xfce，即可登录。
2. vnc：使用vncviewer登录。centos下安装tigervnc、tigervnc-server，启动vncserver，即可登录。
3. dmcp：使用xbrower（xmanager中的组件）。CentOS下安装并配置gdm，即可登录。参考[使用X Manager远程CentOS 7服务器](https://www.zybuluo.com/wuzhimang/note/392271)
    ```
    yum install lightdm
    vi /etc/lightdm/lightdm.conf
        [XDMCPServer]
        enabled=true
        port=177
    systemctl disable gdm
    systemctl enable lightdm
    systemctl stop gdm
    systemctl start lightdm
    systemctl status lightdm
    systemctl stop firewalld.service
    systemctl status firewalld.service
    vi /etc/resolv.conf
        nameserver xx.xx.xx.xx
    ```
4. Widnows中安装xming即可使用。配置参考[鸟哥的Linux私房菜](http://cn.linux.vbird.org/linux_server/0310telnetssh_3.php#xdmcp_client_win)

# 遗留问题：
1. Chrome浏览器在linux是否可以使用（无法下载）

   碰到的问题：
   1. Chrome安装过程中，是在/etc/yum.repo.d/下生成了一个软件源配置文件，直接访问google网站不通。需要配置系统代理。
   2. 配置系统代理后，又发生证书没有导入的问题，需要导入证书。

2. Linux中的中文输入法
   试着在浏览器窗口中下载chrome、google拼音看是否能够成功

3. 普通用户使用firefox，系统重启后firefox的porxy配置、证书配置丢失

4. KDE怎么添加桌面图标（每次都使用命令行启动程序非常低效）

5. KDE怎么直接显示桌面（类似于Windows中的“系统键+D”的效果）
