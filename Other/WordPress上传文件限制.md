

在wordpress后台媒体库中上传图片时注意到下面有：“最大上传文件大小：2M”。由于大于2M的文件无法上传，遂在网络上查找修改上传限制的方法。
注意：本人按下面方法修改完成后，主题无法使用（前端页面加载不出来），但在换成其它主题后前端页面又可以加载出来了，本人不清楚原因。请谨慎操作！！！

1、修改php.ini文件


实际上，这个2M并不是wordpress限制的，而是php服务器限制的。所以，要突破2M限制，就要修改PHP服务器配置文件php.ini，这个文件一般在php安装目录的根目录下，可以在控制台（terminal console）用命令whereis搜索下，如下：

[root@10-7-85-35 ~]# whereis php.ini
php: /usr/bin/php /usr/lib64/php /etc/php.d /etc/php.ini /usr/share/php /usr/share/man/man1/php.1.gz
[root@10-7-85-35 ~]#

可以看到，我的php.ini文件在/etc下，通过SFTP远程修改该文件。