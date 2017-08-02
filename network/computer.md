## PC问题处理

chrome浏览器所有页面都崩溃，把百度相关软件卸载后，删除windows驱动目录下bd0001.sys后，重启Windows恢复
C盘空间太小，使用windirstat程序统计后，发现是系统虚拟内存分页、休眠文件太大所致，把系统休眠禁止掉、虚拟内存分页移动到其他硬盘分区后恢复；三板斧：取消休眠、虚拟内存配置到其他硬盘、磁盘清理
IE/Chrome/Firefox都可以安装AdblockPlus插件

Windows SSH Server：使用FreeSSHd软件，可以在windows上启动SSD Server，可以提供SSH、SFTP能力。使用Putty、WinSCP可以连接。在手机上使用JuiceSSH、AndFTP也可以连接。SSH服务存在中文字符显示问题。

## 手机

ssh agent：JuiceSSH

sftp agent：AndFTP

play商店一直不可用

## 脑图软件

脑图软件是采用json格式描述整个文件的树状视图，向云端上传采用全量传输方式。

分析方法：安装winpcap、windump、wireshark，使用wireshark抓包分析。

## 小红伞

> 原则上来讲，小红伞，就是avira
>
> 或许你指的是独立的avira小红伞杀软，当然，轮杀毒能力应该是小红伞比360强一些。
> 但是诺顿，卡巴斯基，eset比小红伞还要好上一些。
> 也就是说不考虑实际使用情况（钟国互联网情况）的话，你装我上面说的那三个家伙，防护能力理论上来说会更强一些。
> 但我选择使用Windows defender     Windows firewall和UAC

作者：刘大铁棍
链接：https://www.zhihu.com/question/27165468/answer/128345979
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

## windos7格式化硬盘

使用Widnows自带的磁盘管理管理工具。“我的电脑” 右键 “管理”：

![磁盘格式化](img/Windows磁盘管理.png "磁盘格式化")