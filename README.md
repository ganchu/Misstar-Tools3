>使用方法

镜像放到网站可下载目录，创建脚本
install.sh，最好放网站根目录
```
clear

## Check The Router Hardware Model 
model=$(uname -m)
cd /tmp/
curl -s -k http://www.wymlw.cn/demo/rom/$model/mtinstall -o /tmp/mtinstall 
#改自己域名跟文件目录,域名需要http的，https是wget不了的
if [ $? != 0 ];then
    curl -s -k http://mirror1.misstar.com/download/$model/mtinstall -o /tmp/mtinstall
    if [ $? != 0 ];then
    	echo "下载程序失败,即将退出"
        exit
    fi
fi
chmod +x /tmp/mtinstall
/tmp/mtinstall
```
>安装命令

`wget http://www.wymlw.cn/install.sh -O /tmp/install.sh && chmod +x /tmp/install.sh && /tmp/install.sh`

安装后重要的，登录后台后，浏览器要切换IE模式（兼容模式），否则是安装不了插件的
