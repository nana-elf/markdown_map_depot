# Conda安装教程
**# created by Qyl   2020/4/20 **

## 一、为什么要安装Conda

1. 更加安全的python及python包管理
   
   当我们在编写python程序时，我们不可避免的需要安装及导入不同的python包，而我们导入的python包后面又有一个复杂的包的依赖网络。
   
   同时，我们会面临多种多样的开发需求，数据科学、网络后端、爬虫等等，这导致我们需要安装的包可能是完全独立的开发路线，比如说我们在使用tensorflow时可能依赖的是numpy包的1.2.1版本，而在使用网站开发的django包时会依赖于numpy的1.1.1版本，这个时候就会出现冲突了。（这个例子完全虚假，没有根据，只是当作一个例子）

   而Conda引入了一个环境的概念，用户可以创建多个Conda环境，每个环境中都是完全的python环境，安装的包也是完全独立的，python的版本、包的版本也是可以完全不同的。用户可以在不同的环境中进行相对安全的python程序开发。

2. 更加方便的python包管理
   
   Conda为用户安装python包时，提供了更加全面的安装依赖，在你安装某一python包时，能够很好的帮你把此python包的依赖安装完全。p而python自带的pypi包管理器则会存在一些bug（个人经历，不下定论），但是pypi的包会包括一些个人开发者发布的python包，当你在用Conda安装时给你报找不到包的错误时，就拿pypi试一试吧。
   
3. 暂时还没想到更多。但是需要注意，Conda的环境中是有python的，所以当你

## 二、选择Conda的什么版本（Anaconda VS Miniconda）

两个版本都是Conda的发行版，同宗同源，在基础功能上没有任何区别。

1. Anaconda
   
   Anaconda版本，是Conda及一些常用的python开发会用到的包（pandas，numpy等）封装到一起的，当你安装及新建Conda环境时，就会为你预装这些包，方便开箱即用，同时还附带一个前端界面，你可以可视化的去管理python包及Conda环境。
   
   相应的，其体积大，安装慢、占内存、运行慢。


2. 更加方便的python包管理
   
   Miniconda版本，仅仅包括Conda及最基础的python环境，当你安装及新建Conda环境时，只会有一个可运行的python环境，其他的包则需要自己安装。

   相应的，其体积小，安装快，运行快。
   
3. 如果你不是很想秀你的电脑性能及内存，同时也不是那么需求一个前端环境，安装Miniconda是再好不过了。

## 三、安装教程

### windows

1. 系统要求
   
    对于Miniconda 需要 400 MB磁盘空间。

    对于Anaconda 需要最小3 GB磁盘空间可下载和安装。

2. 下载安装包

    下载链接，下载很慢，可以使用迅雷下载：

    Anaconda官网：https://www.anaconda.com/

    Miniconda主页：https://conda.io/miniconda.html

3. 安装

    在windows下可以打开安装包，一直'下一步'就可以了，除了修改一下安装路径外，建议不用进行多余的配置。

4. 环境变量的配置
   
   安装完毕后，需要配置环境变量，让你在命令行输入和python运行时，系统能够找到你的Conda路径和Conda里的python路径。
   
   需要添加的环境变量为：

        注意修改安装路径
        1.安装路径（为了Python检查正常）:前面安装时路径一定要记清楚，默认是C:\ProgramData\Anaconda3
        或C:\ProgramData\Miniconda3

        2.安装路径\scripts（为了conda检查正常）:默认路径是C:\ProgramData\Anaconda3\Scripts
        或C:\ProgramData\Miniconda3\Scripts

5. 安装完毕，可以打开cmd输入"conda"命令进行测试，可能会报需要进行conda init的提示，只需按照提示输入"conda init"即可。

### Linux

1. 系统要求
   
    对于Miniconda 需要 400 MB磁盘空间。

    对于Anaconda 需要最小3 GB磁盘空间可下载和安装。

2. 下载安装包

    下载链接，在Linux里可以使用wget进行下载：

        输入
        wget <下载链接>
    
    下载链接可以通过官网获得

    Anaconda官网：https://www.anaconda.com/

    Miniconda主页：https://conda.io/miniconda.html

3. 安装

        获得文件权限并运行
        chmod 777 文件名.sh
        sh 文件.sh
        然后提示阅读用户许可协议，提示输入安装路径，可以直接默认，键入回车就行了，但是需要记下安装路径
        安装完毕后会提示是否进行conda init，选择yes就行了

4. 环境变量的配置
   
    输入

        export  PATH="安装路径/miniconda3/bin:"$PATH

5. 安装完毕，在命令输入"conda"命令进行测试

## 四、修改镜像源

1. 为什么要修改镜像源
   
    使用conda install 安装环境依赖时，经常会遇到网络超时，导致下载到一半的任务中断，有时这可能与网络环境有关。因此，可使用以下方法进行源切换。
        阿里云 http://mirrors.aliyun.com/pypi/simple/
        清华大学https://pypi.tuna.tsinghua.edu.cn/simple/

1. windows / Linux
   
        conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
        conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
        conda config --set show_channel_urls yes
3. 
   **若在有些系统中没有获取管理管权限，2中的方法无法操作，各系统都可以通过修改用户目录下的 .condarc 文件。Windows 用户无法直接创建名为 .condarc 的文件，可先执行 conda config --set show_channel_urls yes 生成该文件之后再修改。安装清华镜像源参考https://mirrors.tuna.tsinghua.edu.cn/help/**

## 五、基本使用

创建环境
    conda create --name your_env_name
    输入y确认创建。

创建制定python版本的环境
    conda create --name your_env_name python=2.7
    conda create --name your_env_name python=3
    conda create --name your_env_name python=3.5

创建包含某些包的环境
    conda create --name your_env_name numpy scipy

创建指定python版本下包含某些包的环境
    conda create --name your_env_name python=3.5 numpy scipy

列举当前所有环境
    conda info --envs or (conda info -e  # conda environments:)
    conda env list

进入某个环境
    activate your_env_name

退出当前环境
    deactivate 

复制某个环境
    conda create --name new_env_name --clone old_env_name 

删除某个环境
    conda remove --name your_env_name --all