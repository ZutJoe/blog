# 以root权限连接虚拟机

1. 编辑sshd_config文件

   ```shell
   sudo vim /etc/ssh/sshd_config
   ```

   

2. 激活配置

   1. 注释掉 `PermitRootLogin without-password`
   2. 增加一行 `PermitRootLogin yes`

3. 重启ssh服务

   ```shell
   sudo service ssh restart
   ```

   

后面就可以以root权限连接了