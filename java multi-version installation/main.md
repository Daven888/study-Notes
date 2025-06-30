# 一台电脑，如何安装多个JDK版本并保证jdk版本自由切换

## 安装jdk

    在Oracle官网下载不同版本的jdk
<img src="picture\Snipaste_2025-06-30_23-20-58.png">
<img src="picture\Snipaste_2025-06-30_23-21-47.png">

    比如这里下载好了两个jdk版本,

<img src="picture\Snipaste_2025-06-30_23-25-35.png">

## 设置环境变量

    接下来去设置环境变量
<img src="picture\Snipaste_2025-06-30_23-27-37.png">

    点击下方新建,以jdk8和jdk11为例设置三个环境变量JAVA_HOME8,JAVA_HOME11以及JAVA_HOME
    JAVA_HOME8和JAVA_HOME11分别设置为刚刚的安装目录,而JAVA_HOME设置为%JAVA_HOME11%,这
    里的11就是你要用的jdk版本,后面需要用8把这个改成8就行.

<img src="picture\Snipaste_2025-06-30_23-28-04.png">

    然后在系统环境变量下的path变量中添加如下两个值

<img src="picture\Snipaste_2025-06-30_23-28-52.png">

    在这里基本就设置完成了,不过11以后的jdk貌似没有jre文件了,可以检查一下安装的两个jdk目录中是否有jre文件，
    没有的话也可以手动生成.

## 生成jre

    打开所需生成的jdk安装目录,这里我已经生成了
<img src="picture\Snipaste_2025-06-30_23-39-29.png">

    右键点击在终端中打开

<img src="picture\Snipaste_2025-06-30_23-44-15.png">

<img src="picture\Snipaste_2025-06-30_23-44-28.png">

    输入如下指令：`bin\jlink.exe --module-path jmods --add-modules java.desktop --output jre`,点击回车，然后就可以看到目录中生成了jre文件

<img src="picture\Snipaste_2025-06-30_23-44-41.png">

## 测试是否安装成功

    win+r,输入cmd,点击回车
<img src="picture\Snipaste_2025-06-30_23-47-14.png">

    输入`java -version`,显示如下：

<img src="picture\Snipaste_2025-06-30_23-47-33.png">

    自此安装成功！
    






