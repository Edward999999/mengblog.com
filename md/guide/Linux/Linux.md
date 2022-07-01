# Debian中创建文件夹以及文件
1. 创建文件夹
    mkdir /your folder name/
2. 删除文件夹
    rm -rf /your folder name/ 
3. Py文件并编辑
    vim test.py

按insert或i ，编辑 
ESC退出编辑 
:wq保存退出 
4. 执行python文件报错退出
   quit()
# 复制文件/tmp
    cp file.txt /tmp/
## 复制所有文件到目录/tmp
    cp * /tmp/
## -p选项复制文件可以保留源文件得一切属性以及扩展属性
    cp -p file.txt /tmp/
## 使用-R或者-r 可以递归得复制目录下所有文件到另一个目录
    cp -R* /tmp/
# 删除文件
    $ rm file.txt

## 强制删除文件
    $ rm -f file.txt

## 交互式删除文件
    $ rm -i file.txt
    rm: remove regular empty file ‘file.txt’? y

## 详细显示进行的步骤
    $ rm -v file*.txt
    removed ‘file1.txt’
    removed ‘file2.txt’
    removed ‘file3.txt’

## 删除目录不加 -r 会报错
    $ rm folder
    rm: cannot remove ‘folder’: Is a directory

## 正确删除目录
    $ rm -r folder

# 强制删除目录
    $ rm -rf folder

# 删除隐藏文件
    $ rm -rf .*