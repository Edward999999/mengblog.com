# CMD 命令
## ADB命令
查看当前设备分辨率:
    adb shell wm size
查看当前设备屏幕密度（DPI）:
    adb shell wm density

# Git 相关
## 通过git上传代码
1. git add .
2. git commit -m "describe"
3. git pull origin master
4. git push -u  origin master
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