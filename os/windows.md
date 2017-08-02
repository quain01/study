# Windows使用

## 配置启动项

运行"msconfig"，在“启动”页配置系统启动项。

![配置启动项](img/msconfig.png)

## 查看系统启动的端口及对应进程

1. 查看系统启动的端口：运行命令“netstat -ano”

    ```
    C:\>netstat help
    
    显示协议统计和当前 TCP/IP 网络连接。
    ...
      -a            显示所有连接和侦听端口。
      -n            以数字形式显示地址和端口号。
      -o            显示拥有的与每个连接关联的进程 ID。
    ```
    
    ```
    C:\>netstat -ano
    
    活动连接
    
      协议  本地地址          外部地址        状态           PID
      TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       908
      TCP    0.0.0.0:445            0.0.0.0:0              LISTENING       4
      TCP    0.0.0.0:1494           0.0.0.0:0              LISTENING       2176
      TCP    0.0.0.0:2598           0.0.0.0:0              LISTENING       2176
      TCP    0.0.0.0:3389           0.0.0.0:0              LISTENING       1168
      TCP    0.0.0.0:5985           0.0.0.0:0              LISTENING       4
      TCP    0.0.0.0:8081           0.0.0.0:0              LISTENING       1848
      TCP    0.0.0.0:19080          0.0.0.0:0              LISTENING       4
      TCP    0.0.0.0:47001          0.0.0.0:0              LISTENING       4
      TCP    0.0.0.0:49152          0.0.0.0:0              LISTENING       584
      TCP    0.0.0.0:49153          0.0.0.0:0              LISTENING       984
      TCP    0.0.0.0:49154          0.0.0.0:0              LISTENING       476
      TCP    0.0.0.0:49361          0.0.0.0:0              LISTENING       708
      TCP    0.0.0.0:49384          0.0.0.0:0              LISTENING       692
      TCP    0.0.0.0:51139          0.0.0.0:0              LISTENING       4436
      TCP    10.229.34.174:139      0.0.0.0:0              LISTENING       4
    ```

    最后一列就是使用该端口的进程PID

2. 根据PID查询对应进程名字：运行命令“tasklist | findstr <PID>”

    ```
    C:\>tasklist | findstr 584
    wininit.exe                    584 Services                   0        308 K
    ```
