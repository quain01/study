# 计算机安全

## 对计算机的攻击

《黑客入门全程图解》描述了早期widnows系统的漏洞以及攻击方式。

- Netbios漏洞：在网络上扫描共享文件，win9x的共享文件没有密码保护，win2000虽有密码保护但是可以暴力破解。可以查看、修改远程计算机上的文件。
- IPC漏洞：通过ipc漏洞（获取登录用户列表）、暴力破解登录远程计算机。
- Win2000输入法漏洞：通过win2000输入法漏洞，在登录界面调出windows资源管理器，从而使用net命令开启guest访问或创建新的用户，实现非法登录计算机。

## 恶意程序

参考[【电脑知识】木马、病毒和蠕虫的区别](http://tieba.baidu.com/p/2415463306)，里面描述到了木马、病毒、蠕虫的区别，以及各种恶意程序的典型代表，从典型代表入手，熟悉各种恶意程序的感染路径，危害方式。

## Web漏洞

早年对网站的一种攻击方式：获取网页代码（asp），分析其对数据库的查询sql的写法，从而构造特定的输入信息，查询数据库的信息，获取到管理员信息，登录网站的远程管理portal，进行对网站的攻击，例如植入木马等。

SQL注入：分析网页代码（asp、php），分析其构造sql语句的方式，从而通过构造特定的输入信息，控制网页中sql语句的执行，从而完成攻击（非法获取信息、绕过认证程序等）