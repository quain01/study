# CentOS硬盘安装

1. 在一个磁盘分区根目录中放入iso文件
2. 把iso文件中isolinux、image目录解压出来
3. 修改grub引导文件（/boot/grub/menu.lst），增加一个启动项
    ```
    title Install CentOS 7.0
    root (hd0,2)
    kernel /isolinux/vmlinuz linux repo=hd:/dev/sda3:/
    initrd /isolinux/initrd.img
    ```
   注意：root行用于定义vmlinuz、initrd.img所在分区，kernel行的repo用于定义iso文件所在分区，需要根据实际情况修改。（hd0,2）对应sda3。

# 注意

1. CentOS安装过程中会修改安装硬盘的MBR记录，如果不想让其修改，需要事先把MBR记录备份下来，在完成安装后再覆盖回去。
2. CentOS 7使用grub2，MBR记录可能不止一个扇区，把第一个扇区后的其他扇区清空后，硬盘引导不起来了。
    ```
    dd if=/dev/sda of=backup bs=512 count=64   用于备份
    dd if=backup of=/dev/sda bs=512 count=64   用于恢复
    ```

# 故障处理

1. 服务器中有硬盘（非系统盘）故障，该硬盘上的文件系统无法挂载，导致所有文件系统变成只读，系统盘中的/etc/fstab无法修改。使用如下命令重新挂载，并修改/etc/fstab。
    ```
    # mount -o remount rw /
    ```