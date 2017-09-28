# 删除文件行

[用sed删除第一行、最后一行或增加删除某行](http://www.quwenqing.com/read-167.html)

1、删除文档的第一行

    sed -i '1d' <file>

2、删除文档的最后一行

    sed -i '$d' <file>

3、在文档指定行中增加一行

    例如文档如下：
    
    echo "1";
    
    echo "2";
    
    echo "4";
    
    echo "5"; 
    
    想要在echo "2";后面加上一条echo "3";可以用如下命令
    
    sed -i '/echo "2";/aecho "3";'  <file>
    
    之所以用分号，是因为文本中本来就有。也就是说分号不是必须的！
    
    抽象出来就是： sed -i '/* /a*' <file>

4、删除文件中的一行

	sed -i '3d' <file>

5、删除文件中包含某个关键字开头的所有行

	sed -i '/^QWQ/d' <file>

6、删除文件中包含某个关键字的所有行 

	sed -i '/QWQ/d' <file>