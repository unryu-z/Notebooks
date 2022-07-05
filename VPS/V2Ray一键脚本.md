# V2Ray一键脚本

于2019年12月20日由[**跳越者**](https://hijk.pp.ua/author/admin/)发布

> 使用过程中遇到问题，请先仔细参考 [科学上网常见问题](https://hijk.pp.ua/vpn-faq/)。如果不能解决您的问题，欢迎到 [网络跳越论坛](https://hijk.club/) 或 TG群组 https://t.me/hijkclub 交流

今天做了**CentOS 7/8**系统的v2ray的一键安装脚本，目前已经上传到 [Github](https://github.com/hijkpw/scripts)。如果您的系统是**Ubuntu**，请参考这个教程： [v2ray一键脚本Ubuntu版](https://hijk.pp.ua/ubuntu-one-click-install-v2ray/)

**提示：**这是自己搭建科学上网环境的第三步，请确认已经做了前两步：

1. 购买服务器。想要服务器速度快请参考 [搬瓦工VPS购买教程](https://hijk.pp.ua/bandwagonghost-buy-vps-tutorial/) 或 [购买AkkoCloud德国、美西CN2 GIA VPS](https://www.akkocloud.com/aff.php?aff=122&gid=7) ，想ip被封后免费换请参考：[购买vultr服务器超详细图文教程](https://hijk.pp.ua/vultr-buy-vps-tutorial/)
2. 连接到服务器，Windows系统请参考 [Bitvise连接Linux服务器教程](https://hijk.pp.ua/bitvise-connect-linux-server-tutorial/)，mac用户请参考 [Mac电脑连接Linux教程](https://hijk.pp.ua/mac-connect-to-linux-tutorial/)

**注意：**

\1. 如果你有域名，强烈建议使用 [v2ray带伪装一键脚本](https://hijk.pp.ua/v2ray-one-click-script-with-mask/)，能有效应付近些天的疯狂封杀，提供稳如狗的体验！

\2. 理论上只要流量够、服务器扛得住，同一个配置支持无数人、无限设备使用。如果想为不同的人配置不同的id，请参考：[v2ray多用户配置](https://hijk.pp.ua/v2ray-multiple-users/)；

\3. 本站的一键脚本与其他网站的不能混合使用，**如果之前运行过其他的请先卸载**，否则可能导致无法上外网！

\4. **BBR换成魔改BBR/BBR Plus/锐速清参考：[安装魔改BBR/BBR Plus/锐速(Lotserver)](https://hijk.pp.ua/install-bbr-plus-lotserver/)；**

\5. 这两天官方脚本会出现“unzip: cannot find zipfile directory in one of /tmp/v2ray/v2ray.zip or
/tmp/v2ray/v2ray.zip.zip, and cannot find /tmp/v2ray/v2ray.zip.ZIP, period.
Failed to copy V2Ray binary and resources.”的抽风现象，本站一键脚本已经做了兼容修复；

\6. 近日v2ray爆出裸tcp协议流量精确识别的漏洞，建议更新服务端和客户端，或使用 [v2ray带伪装一键脚本](https://hijk.pp.ua/v2ray-one-click-script-with-mask/)。

## 使用教程

登录到服务器（windows请参考 [Bitvise连接Linux服务器教程](https://hijk.pp.ua/bitvise-connect-linux-server-tutorial/)，mac用户请参考 [Mac电脑连接Linux教程](https://hijk.pp.ua/mac-connect-to-linux-tutorial/)），在终端（黑框框）输入如下命令：

```
bash <(curl -sL https://raw.githubusercontent.com/hijkpw/scripts/master/centos_install_v2ray.sh)
```

按回车键，屏幕出现 “**请设置v2ray的端口**[1-65535]” 的提示，输入一个你希望的端口号（例如12345，**不能是22**）。接下来屏幕上会疯狂出现一些你看得懂也可能看不懂的东西，**如果安装过程卡住，请耐心等待几分钟；**期间网络断开（windows上表现为黑框框中或者顶部标题出现“disconnected”，mac表现为终端出现“closed by remote host”或”broken pipe”），请重新连接后再次执行命令。安装成功后，会输出配置信息，截图如下：



v2ray一键安装脚本

**到此服务端配置完毕**，服务器可能会自动重启(**如果没提示重启则不需要**)，windows终端出现“disconnected”，mac出现“closed by remote host”说明服务器成功重启了。

V2ray一键脚本做了如下事情：

1. 更新系统到最新版
2. 安装bbr加速模块
3. 安装v2ray并设置开机启动

## 客户端下载

接下来是**科学上网最后一步**：下载客户端，并参考页面中的配置教程进行配置：

[v2ray windows客户端下载](https://hijk.pp.ua/v2ray-windows-client-download/)

[v2ray安卓客户端下载](https://hijk.pp.ua/v2ray-android-client-download/)

[v2ray mac客户端下载](https://hijk.pp.ua/v2ray-mac-client-download/)

[v2ray ios客户端下载](https://hijk.pp.ua/v2ray-ios-client-download/)

下载客户端配置好后，就可以愉快的上外网了！

## 其他

\1. 查看v2ray配置/运行状态：`bash <(curl -sL https://raw.githubusercontent.com/hijkpw/scripts/master/centos_install_v2ray.sh) info`;

\2. v2ray管理命令：启动：`systemctl start v2ray`，停止：`systemctl stop v2ray`，重启：`systemctl restart v2ray`;

\3. 更改端口、alterid最简单的办法：重新运行一键脚本；

\4. 更新v2ray到最新版：`bash <(curl -L -s https://install.direct/go.sh)`

\5. 卸载v2ray： `bash <(curl -sL https://raw.githubusercontent.com/hijkpw/scripts/master/centos_install_v2ray.sh) uninstall`

## 参考

\1. [v2ray教程](https://tlanyan.me/v2ray-tutorial/)

