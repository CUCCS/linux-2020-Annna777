## 实验：动手实战systemd
  *****
### 实验要求  
* 学习systemd开机自启动管理机制
* 动手实战systemd并完成自查清单
  *****
### 实验过程
##### 系统管理：  
[![asciicast](https://asciinema.org/a/nFfWnUONSiwBTsin2JxKmgtGB.png)](https://asciinema.org/a/nFfWnUONSiwBTsin2JxKmgtGB)
##### Unit及其配置文件：  
[![asciicast](https://asciinema.org/a/B5s0hagcYnn9KkucVGJgZFbqo.png)](https://asciinema.org/a/B5s0hagcYnn9KkucVGJgZFbqo)  
##### Target+日志管理：  
[![asciicast](https://asciinema.org/a/Xqg3WDJhgOb3oqNDyzEKaqCF7.png)](https://asciinema.org/a/Xqg3WDJhgOb3oqNDyzEKaqCF7)  
##### 实战篇：  
[![asciicast](https://asciinema.org/a/Vvi4bw99viJwWMiGUVDnlkzDu.png)](https://asciinema.org/a/Vvi4bw99viJwWMiGUVDnlkzDu)
  
  *****
### 自查清单
##### 1. 如何添加一个用户并使其具备sudo执行程序的权限？
* 添加新用户: ```adduser username``` 
* 使其具备sudu执行权限:   
  ```sudo usermod -a -G sudo username```
##### 2. 如何将一个用户添加到一个用户组?  
* ```sudo usermod -a -G groupname username```  
##### 3. 如何查看当前系统的分区表和文件系统详细信息？
* 查看系统分区表：```sudo sfdisk -l```
* 查看文件系统详细信息：```df -a```
##### 4. 如何实现开机自动挂载Virtualbox的共享目录分区？  
* 添加共享文件夹，对应创建虚拟机内目录/mnt/share
* 挂载文件夹：  
  ```sudo mount -t vboxsf sharename /mnt/share```  
* 实现开机自动挂载：  
  ```vim /etc/rc.local```打开```/etc/rc.local```后添加：  
  ```mount -t vboxsf sharename /mnt/share```
##### 5. 基于LVM（逻辑分卷管理）的分区如何实现动态扩容和缩减容量？
* 逻辑卷扩容：```lvextend -L +size /dev/dir```
* 缩减容量：```lvreduce -L -size /dev/dir```
##### 6. 如何通过systemd设置实现在网络连通时运行一个指定脚本，在网络断开时运行另一个脚本？  
* 修改systemd-networkd.service配置文件中的[Service]区块  
  ```ExecStartPost = 联通时脚本```  
  ExecStopPost = 断开时脚本```
* 重载修改过的配置文件  
  ```sudo systemctl daemon-reload```
* 重新启动，让修改生效  
  ```sudo systemctl restart```  
  ```systemd-networkd.service```

##### 7. 如何通过systemd设置实现一个脚本在任何情况下被杀死之后会立即重新启动？实现杀不死？  
* 修改配置文件  
  ```sudo systemctl vi servicename``` 
* 设置[Service]区块  
  ```Restart=always``` 
* 重载修改过的配置文件  
  ```sudo systemctl daemon-reload```  
* 重新启动，让修改生效  
  ```sudo systemctl restart servicename```  
  *****
### 参考资料  
* http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-part-two.html  
* http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html  
* https://jingyan.baidu.com/article/2f9b480d9bd58441ca6cc25e.html
* https://tsov.net/home/view/282/
