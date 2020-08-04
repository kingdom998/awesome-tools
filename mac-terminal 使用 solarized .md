# [mac 终端 使用 solarized 主题设置语法高亮](https://www.cnblogs.com/cocoajin/p/3729345.html)

mac 终端 使用 solarized 主题设置语法高亮

先来看看 solarized 在 mac 终端上的效果图片

![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wps853NMC.jpg) 

一：先下载 solarized

 官网下载：[https://github.com/altercation/solarized](http://ethanschoonover.com/solarized)

​       [ http://ethanschoonover.com/solarized](http://ethanschoonover.com/solarized)

二：下载完之后，解压zip, 双击 solarized/osx-terminal.app-colors-solarized 下的 两个主题，一个是 Dark,一个是 light, 根据个人喜好，这里我使用的是Dark,双击Dark即可安装到 mac终端的配置文件中；

  然后配置终端：先打开终端：终端---偏好设置---设置----选中 Solarized Dark主题---设置默认，别忘记点击一下右下角的默认按钮设置默认

   ![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wps5T5sJI.jpg)

三：配置solarized

1: 打开终端：执行 

sudo cp /usr/share/vim/vimrc ~/.vimrc   把默认的.vimrc复制到个人配置文件中一份

![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wpsewKGHC.jpg) 

2：在 新建 colors 目录终端执行：  sudo mkdir ~/.vim/colors

![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wps3uiUpd.jpg) 

3: 移动 solarized 配置文件到 colors目录下

执行：cd solarized/vim-colors-solarized/colors/

sudo mv solarized.vim ~/.vim/colors/

![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wpsNV6ivW.jpg) 

4：启用 solarized主题

终端：执行 sudo vim ~/.vimrc 

在文件里面添加：

此为开启 dark主题

syntax enable
set background=dark
colorscheme solarized

 

开启light主题

syntax enableset background=light

colorscheme solarized

![img](file:////private/var/folders/hq/2_lyl_hn4x546wqmhv8_k3l40000gn/T/com.kingsoft.wpsoffice.mac/wps-kd/ksohtml/wpskkZys6.jpg) 

然后保存退出---重新打开 终端即可；

 