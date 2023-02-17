
## 安装 Samba

```shell
sudo apt-get install samba
sudo apt-get install smbclient
```

## 修改配置文件

```shell
sudo vim /etc/samba/smb.conf
```

```ini
[develop_share] 
valid users = lkt 
path = /
public = yes 
writable = yes 
create mask = 0644 
force create mode = 0644 
directory mask = 0755 
force directory mode = 0755 
available = yes
```

|    参数     |      意义      |
| :---------: | :------------: |
|    share    |    共享名称    |
|    path     |  共享文件路径  |
| vaild users |    添加用户    |
|   comment   |    描述信息    |
|   public    | 是否所有人可见 |
|  writable   |  是否有写权限  |

## 添加用户

```shell
sudo smbpasswd -a lkt
```

添加完用户之后需要设置密码

## 重启服务器

```shell
sudo /etc/init.d/samba restart
或
sudo /etc/init.d/smbd restart
```

## 在Windows下访问samba服务

格式

```shell
\\ + ip
```

然后根据图片相关步骤设置

![image-20230217093735676](..\Linux\Linux 下 Samba服务器的构建.assets\image-20230217093735676.png)
