# 笔记库
# CMD 命令
## ADB命令
查看当前设备分辨率:

    adb shell wm size
查看当前设备屏幕密度（DPI）:

    adb shell wm density

# Git 相关
## 通过git上传代码
    git add .
    git commit -m "describe"
    git pull origin master
    git push -u  origin master
## 怎么设置Github代码仓库私有
第一步：点击项目列表，进入设置页面

![图片](https://github.com/Edward999999/mengblog.com/blob/master/md/guide/pic/makeRepositoriesPrivicy1.png?raw=true)

第二步：选择`Setting`

![图片](https://github.com/Edward999999/mengblog.com/blob/master/md/guide/pic/makeRepositoriesPrivicy2.png?raw=true)

第三步：下滑到最底部点击`Change visibility`

![图片](https://github.com/Edward999999/mengblog.com/blob/master/md/guide/pic/makeRepositoriesPrivicy3.png?raw=true)

第四步：输入确认信息

![图片](https://github.com/Edward999999/mengblog.com/blob/master/md/guide/pic/makeRepositoriesPrivicy4.png?raw=true)

## 怎么让github仓库中的图片展示在docsify项目中
1. 将图片上传至gtihub
2. 打开图片右键图片复制地址

ps：不能直接复制图片链接，图片链接缺少`?raw=true`

# Docsify使用指南
## 快速开始
推荐全局安装 docsify-cli 工具，可以方便地创建及在本地预览生成的文档。

    npm i docsify-cli -g

## 初始化项目
如果想在项目的 `./docs` 目录里写文档，直接通过 `init` 初始化项目。

    docsify init ./docs

## 开始写文档
初始化成功后，可以看到 `./docs` 目录下创建的几个文件

+ `index.html` 入口文件
+ `README.md` 会做为主页内容渲染
+ `.nojekyll` 用于阻止 GitHub Pages 忽略掉下划线开头的文件

直接编辑 `docs/README.md` 就能更新文档内容，当然也可以添加[更多页面](https://docsify.js.org/#/zh-cn/more-pages)。

## 本地预览
通过运行 `docsify serve` 启动一个本地服务器，可以方便地实时预览效果。默认访问地址 http://localhost:3000 。

    docsify serve docs

更多命令行工具用法，参考 [docsify-cli 文档](https://github.com/docsifyjs/docsify-cli)。


## 手动初始化
如果不喜欢 npm 或者觉得安装工具太麻烦，我们可以直接手动创建一个 index.html 文件。

index.html

    <!DOCTYPE html>
    <html>
    <head>
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta charset="UTF-8">
    <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/vue.css">
    </head>
    <body>
    <div id="app"></div>
    <script>
        window.$docsify = {
        //...
        }
    </script>
    <script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
    </body>
    </html>
如果你的系统里安装了 Python 的话，也可以很容易地启动一个静态服务器去预览你的网站。

    cd docs && python -m SimpleHTTPServer 3000

    cd docs && python -m http.server 3000
## Loading 提示
初始化时会显示 `Loading...` 内容，你可以自定义提示信息。

    <!-- index.html -->
    <div id="app">加载中</div>
如果更改了 `el` 的配置，需要将该元素加上 `data-app` 属性。

    <!-- index.html -->
    <div data-app id="main">加载中</div>
    <script>
        window.$docsify = {
        el: '#main'
        }
    </script>
对比 [el 设置](https://docsify.js.org/#/zh-cn/configuration?id=el)。

# markdown语法
## 文字背景色
使用方法：双反逗号，即逐渐盘数字键1左侧按键

效果展示： `背景色`

## 代码块展示
使用方法：选中代码块按Tab键

效果展示：

    hello，world

## 无序列表
使用方法：'+' '-' '*'均可标记为无序列表，且可以通过Tab键嵌套

+ 三字经
    - 人之初，性本善
+ 千字文
    * 天地玄黄，宇宙洪荒


## 超链接
使用方法：英文中括号[]填写内容，()内填写链接

效果展示：[百度](https://www.baidu.com)



## 在VS code中预览Markdown文件
1. VS code市场中搜索并安装Markdown Preview Enhanced插件
2. 在md文档页面按ctrl+shift+v

## 在Markdown中插入图片
使用方法：
1. 英文叹号+中括号![图片]，()内填写链接
2.  _![图片]：如果图片无法加载，默认显示”图片“文字
ps:本地路径一定要注意路径的/方向，反了可获取不到
效果展示：![图片](https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg)


# Linux使用指南
## Debian中创建文件夹以及文件
### 创建文件夹
   
    mkdir /your folder name/
### 删除文件夹
    rm -rf /your folder name/ 
## 创建Py文件并编辑
    vim test.py

按insert或i ，编辑 

ESC退出编辑 

:wq保存退出 
### 运行python程序
程序后台运行`nohup python main.py &`
查看后台运行的进程`ps -aux`
杀死进程 `kill -9 进程号`
### 执行python文件报错退出
    quit()
## 复制文件/tmp
    cp file.txt /tmp/
### 复制所有文件到目录/tmp
    cp * /tmp/
### -p选项复制文件可以保留源文件得一切属性以及扩展属性
    cp -p file.txt /tmp/
### 使用-R或者-r 可以递归得复制目录下所有文件到另一个目录
    cp -R* /tmp/
## 删除文件
    $ rm file.txt

### 强制删除文件
    $ rm -f file.txt

### 交互式删除文件
    $ rm -i file.txt
    rm: remove regular empty file ‘file.txt’? y

### 详细显示进行的步骤
    $ rm -v file*.txt
    removed ‘file1.txt’
    removed ‘file2.txt’
    removed ‘file3.txt’

### 删除目录不加 -r 会报错
    $ rm folder
    rm: cannot remove ‘folder’: Is a directory

### 正确删除目录
    $ rm -r folder

### 强制删除目录
    $ rm -rf folder

### 删除隐藏文件
    $ rm -rf .*
[Debian安装Python](md/guide/Python/installPythonOnDebian.md)
# 在Debian上安装Nodejs教程
    sudo apt update
    sudo apt install nodejs npm
    nodejs --version

# 在Debian上安装Python教程
在 Debian 上构建 Python 3.9 是一个相对简单的过程，只需几分钟。

1. 安装构建Python源所需的包：
    
        sudo apt update
        sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget

2. 使用以下curl命令从Python下载页面下载最新版本的源代码：

        curl -O https://www.python.org/ftp/python/3.9.9/Python-3.9.9.tgz
    
    版本号可以根据最新得Python版本更新，在撰写本文时，最新版本是3.9.9。

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


### PyInstaller报错
安装之后通过打包命令 `pyinstaller -F -w -i aaa.ico zzz.py `打包提示错误

    PyInstaller cannot check for assembly dependencies.
    Please install PyWin32 or pywin32-ctypes.


修改 `D:\Program Files\Python\Lib\site-packages\PyInstaller\compat.py` 201、202行

    if is_win:
    try:
        # from win32ctypes.pywin32 import pywintypes  # noqa: F401, E402
        # from win32ctypes.pywin32 import win32api  # noqa: F401, E402
        import pywintypes
        import win32api
中的from 为import


## 打包
    1. 打包命令`pyinstaller -F main.py`
    2. 进入打包好得执行文件存放目录`cd dist/`
    3. 尝试执行 `./main` 

       
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

