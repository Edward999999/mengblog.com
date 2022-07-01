# 在Debian上安装Python教程
在 Debian 上构建 Python 3.9 是一个相对简单的过程，只需几分钟。

1. 首先安装构建Python源所需的包：
    sudo apt update 
    sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget
2. 使用以下curl命令从Python下载页面下载最新版本的源代码：
    curl -O https://www.python.org/ftp/python/3.9.9/Python-3.9.9.tgz
    
版本号可以根据最新得Python版本更新
在撰写本文时，最新版本是3.9.9。

3. 下载完成后解压tgz压缩包
    tar -xf Python-3.9.9.tgz

4. 导航到Python源目录并运行configure脚本，该脚本将执行大量检查以确保系统上存在所有依赖项：
先切换到Python源目录
    cd Python-3.9.9 
再运行configure脚本
    ./configure --enable-optimizations --enable-share

--enable-optimizations选项将通过运行多个测试来优化Python二进制文件，这将使构建过程变慢。

5. 运行make以启动构建过程：

    make -j 2

为了缩短构建时间，请根据处理器修改-j标志。 如果你不知道处理器的核心数，可以通过键入nproc来找到它。 我的系统有2个内核，所以我使用-j2标志。

6. 构建完成后，通过以具有sudo访问权限的用户身份运行以下命令来安装Python二进制文件：

    sudo make altinstall

不要使用标准的make install，因为它会覆盖默认的系统python3二进制文件。

7. 此时，Python 3.9.9已安装在你的Debian系统上并可以使用。 你可以输入以下命令进行验证：

    python3.9 --version

输出版本信息

Python 3.9.9

## 修改软连接：

查了下，python3.9,这个命令是在 /usr/local/bin/python3.9

直接输入python3.9也是可以执行的。但这个格式不方便，我想改成python

    sudo rm /usr/bin/python
    sudo rm /usr/bin/python2
    sudo rm /usr/bin/python2.7
    sudo ln -s /usr/local/bin/python3.9 /usr/bin/python

以后直接输： python就可以了

pip3.9，也改成pip了

    sudo ln -s /usr/local/bin/pip3.9 /usr/bin/pip
## 安装打包工具
1. 执行以下命令`pip install pyinstaller`
2. 执行升级命令`python -m pip install --upgrade pip`
3. 修改打包工具软连接
    sudo ln -s /usr/local/bin/python3.9/bin/pyinstaller /usr/bin/pyinstaller
## 打包
    1. 打包命令`pyinstaller -F main.py`
    2. 进入打包好得执行文件存放目录`cd dist/`
    3. 尝试执行 `./main` 
    4. 程序后台运行`nohub ./main &`
       
## 打包报错
    * On Debian/Ubuntu, you need to install Python development packages:
    * apt-get install python3-dev
    * apt-get install python-dev
    * If you are building Python by yourself, rebuild with `--enable-shared` (or, `--enable-framework` on macOS)`
1. 重新执行安装步骤4-6
2. 再执行下属命令
    cp libpython3.so libpython3.9.so.1.0 /usr/lib64/




参考：[python部署+打包](https://www.cnblogs.com/hejj-bk/articles/15732624.html)
[后台运行程序](https://blog.csdn.net/qq_41035283/article/details/123532615)