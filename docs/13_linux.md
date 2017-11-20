### MySql
```
登录mysql			mysql -h demo180.test.com -upriestuser -ppriestuser
显示数据库			show databases;
切换数据库			use databases;
显示表				show tables;
创建数据库			create database name;
删除数据库，不提示	drop database name;
显示表结构			describe tableName;
显示版本，当前日期	select version(),current_date;

删除信息			delete from tableName where clumn='aa';
```


###Linux
```
sudo				以其他身份来执行命令。预设值为root
ll或ls				显示文件
mv fileName 路径	移动文件
rz -be				上传文件
rz -be -y			删除原有文件并上传同名文件
sudo su - root		切换到root用户
su - userName		切换到普通用户
```

```
3.4.4.0 process-site.properties文件所在位置：/usr/leap/3.4.4.0/process/var/lib/process/webapps/TaskSchedule/WEB-INF/classes
204部署路径：
/usr/leap/3.4.3.1/process/var/lib/process/webapps/TaskSchedule
重启路径：/usr/leap/3.4.3.1/process/var/lib/process/bin
重启命令：./jetty.sh start
183部署路径：/var/lib/priest/webapps/TaskSchedule/views
文件替换时使用用户：processuser
```

