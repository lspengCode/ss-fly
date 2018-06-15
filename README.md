一键脚本安装shadowsocks/shadowsocksR/V2Ray + 开启bbr
---

一键脚本搭建shadowsocks/shadowsocksR/V2Ray + 设置开启自启动 + 升级内核&开启bbr加速。

## 支持系统
CentOS 6+
Debian 7+
Ubuntu 12+

## 使用教程
一键搭建ss/ssr：[一键脚本搭建shadowsocks+开启bbr](https://www.flyzy2005.com/fan-qiang/shadowsocks/install-shadowsocks-in-one-command/)

一键搭建V2Ray：[一键脚本搭建V2Ray+配置与优化](https://www.flyzy2005.com/v2ray/how-to-build-v2ray/)

### 运行搭建ss脚本代码
````
ss-fly/ss-fly.sh -i flyzy2005.com 1024
````
其中flyzy2005.com换成你要设置的shadowsocks的密码即可（这个flyzy2005.com就是你ss的密码了，是需要填在客户端的密码那一栏的），密码随便设置，最好只包含字母+数字，一些特殊字符可能会导致冲突。而第二个参数1024是端口号，也可以不加，不加默认是1024~（举个例子，脚本命令可以是ss-fly/ss-fly.sh -i qwerasd，也可以是ss-fly/ss-fly.sh -i qwerasd 8585，后者指定了服务器端口为8585，前者则是默认的端口号1024，两个命令设置的ss密码都是qwerasd）

注：如果需要改密码或者改端口，只需要重新再执行一次搭建ss脚本代码就可以了，或者修改/etc/shadowsocks.json这个配置文件。

### 相关ss操作
````
修改配置文件：vim /etc/shadowsocks.json
停止ss服务：ssserver -c /etc/shadowsocks.json -d stop
启动ss服务：ssserver -c /etc/shadowsocks.json -d start
重启ss服务：ssserver -c /etc/shadowsocks.json -d restart
````

### 卸载ss服务
````
sss -fly/ss-fly.sh -uninstall
````
