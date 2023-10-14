# 建立虚拟机以及安装ubuntu  
## 第一步 寻找资源下载VMware  
![Alt text](f29cc8947be5365758ec4642c2fa3c8.png)![Alt text](68f39d6e6dbc6f8da89b8a44dc4bb77.png)  
## 安装完成后打开，创建虚拟机  
![Alt text](d91eac204480540755567c815f3bca4.png)
## 第二步 前往ubuntu官网下载安装ubuntu![Alt text](1b90572ec041eff9819502734a13054.png)
![](be07d8e84848b943cc6f27b9ec17c4e.png)
## 随后在vmware的虚拟机设置中更改设置，选择Ubuntu的光盘映像文件![Alt text](988cfe83c834efdf1809cca533dd2d2.png)
## 最后一步，启动虚拟机，大功告成！
### ***加分项1.用remote插件连接VScode和Ubuntu***
### 第一步 在vscode中下载remote development插件![Alt text](image-4.png)
### 接下来，在ubuntu中获取地址![Alt text](image-6.png)
找到192.168.67.128
### 输入指令sudo apt-get install ssh安装ssh服务器
![Alt text](image-7.png) 
输入命令service ssh start
![Alt text](image-10.png)
启动服务器运行
然后在remote control中点击新建远程
***并在设置中调试config文件***![Alt text](image-11.png)
输入IP地址以及用户名
![Alt text](d8251c39b1a6753ba5adb07bacd4784-1.png)输入密码
![](34b9e9388326ffd03eff756b5a03514.png)成功连接！
最后可以输入service ssh stop停止连接！![Alt text](64ccc546284f2d096c6debab8396dff-1.png)
### ***加分项2.配置好基于ssh的远程服务器登录***
我选择在虚拟机中的ubuntu中配置远程服务器
首先，打开Ubuntu终端，输入ssh-keygen生成密匙![](image-12.png)
容易得知，两个id_rsa中有后缀的那一个文件为公钥，另一个为私钥
然后输入命令cd .ssh进入文件夹，输入命令cat id_rsa打开文件，查看密匙![Alt text](ca5f76cdbc08395ee5853503ec6b680.png)
复制密匙，然后在终端输入sudo  apt install vim安装vim![Alt text](b6223147a4892cecb965b5a741d2548.png)
再输入vim authorized keys打开文件，将复制的密匙输入进去![](825bb77546fda8112378616e0895ecb.png)至此ssh配置大致完成
最后，在命令界面输入service ssh start开启服务
回到windows终端输入Ubuntu中ip地址和用户名，按提示键入密码即可![Alt text](f2a5218fefd043c2cafd2f7e3385aaa.png)
至此搭建远程服务器成功！~