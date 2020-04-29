# Pytorch安装教程
**# created by Qyl   2020/4/23 **

**# tip：建议使用conda再创建一个环境，并在新环境中安装pytorch**

## 一、什么是 PyTorch?

PyTorch 是一个基于 Python 的科学计算包，主要定位两类人群：

    ● NumPy 的替代品，可以利用 GPU 的性能进行计算。
    ● 深度学习研究平台拥有足够的灵活性和速度


## 二、PyTorch 安装


1. Windows 
   
    (1) 打开https://pytorch.org/ 可以选择安装器，Python版本，CUDA 版本。

    (2) 复制相应语句到命令行即可
        ![avatar](https://github.com/nana-elf/markdown_map_depot/blob/master/pc1.png?raw=true)

    (3) conda list 查看安装的包 or import torch


2. Linux
   
    (1) (2)同上 

3. $\color{#FF0000}{需要选择CUDA版本时候}$
    ### windows 
         ● 查看gpu型号（几乎所有gpu支持cuda）：a.软件管家b.开始菜单_设备管理器_显示适配器c.任务管理器_性能
         ● 命令行输入nvida-smi确定cuda版本
    ### linux
         ● 命令行输入nvida-smi确定cuda版本 
         ● torch.cuda.is_availiable()——Ture
    
## 三、ubuntu系统连接


1. 命令行操作
   ssh 用户名@ip<font color=red>（需要挂校园网VPN）</font>
   
2. Teamviewer

    (1) 先通过命令行下载<font color=red>（需要取得管理员权限）</font>

3. SecureCRT（别人推荐，说好用）


## 四、ubuntu运行文件

1. 文件上传
   
    a. **下载winscp用于文件管理**（别人推荐，说好用）
    
     <img src="https://github.com/nana-elf/markdown_map_depot/blob/master/333.png?raw=true" width = "600" height = "450" alt="图片名称" align=center />

    b. **下载jupyter lab**: conda install jupyter lab 
        <font color=red>（代码运行结果看起来很爽，特别是要画图，有各种插件，如果安装成功很香）</font>
        <font color=red>（此命令可后台挂起程序）</font>：nohup jupyter lab --ip=10.12.131.114 --no-browser --allow-root > jupyter.log 2>&1 &

    c. **x manager6**（实验室内部推荐使用，但是我没成功）
       (1) 用xshell连接服务器，进行命令行操作；用xftp上传文件，主要是这两个
       (2) 端口号选择22

    d. **命令行**
        Eg. scp -r localfile.txt username@192.168.0.1:/home/username/
        其中，
        １）scp是命令，-r是参数
        ２）localfile.txt 是文件的路径和文件名
        ３）username是服务器账号
        ４）192.168.0.1是要上传的服务器ip地址
        ５）/home/username/是要拷入的文件夹路径

2. 文件运行
    
    a. 命令行：python XX.py
    b. 或者下载的软件内自行操作 

3.  查看代码运行情况
    
    a. nvidia-smi
   

## 五、linux 系统常用命令

查看文件目录    

        lsattr -a:显示所有文件和目录，包括隐藏文件
        lsattr -b:显示目录名称，而非其内容

文件打开

        cd 文件夹 -----进入文件夹
        cd ..                  返回上一级目录
        cd ../..               返回上两级目录
        cd或cd ~           返回home目录
        cd - 目录名       返回指定目录

创建文件夹

        mkdir (文件名)

删除文件

        rm -f (文件名)
        rm -rf (文件名):强制删除
