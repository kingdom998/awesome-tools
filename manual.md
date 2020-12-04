## shell
* 批量重命名文件夹
```
abc="-service" && for i in $(find . -type d -maxdepth 1  -name "*$abc"); do mv $i ${i:0:-8};  done;
 ```
 
## mac 环境

* [brew 安装配置](https://www.jianshu.com/p/0cea9650918d)
```
软件列表：item2 git go goland vscode wps typora
```

* php-admin 本地部署
```
brew 安装 php-7.2
```

* 启动 php-fgm 报错
```  
* failed to open configuration file '/private/etc/php-fpm.conf
* [o pool defined. at least one pool section must be specified in config file](https://www.cnblogs.com/xiaozong/p/5458169.html)
```

## Centos 环境
* [ssh配置](https://segmentfault.com/a/1190000013759207)
```
ssh-keygen -t rsa -C “995350347@qq.com” 
cat ~/.ssh/id_rsa.pub # 查看
ssh -T git@github.com   # 验证
```
* [将 Centos 的 yum 源更换为国内的阿里云源](https://www.jianshu.com/p/4aa7b63f9026)
* 安装基础工具
```
yum install -y epel-release yum-utils redhat-lsb
1. yum install -y supervisor # 安装软件
2. systemctl enable supervisord # 开机启动
3. systemctl start supervisord # 启动服务
```

* git wget  bash-completion zsh oh-my-zsh
    * [安装HomeBrew以及解决Could not resolve host: raw.githubusercontent.com问题](https://www.jianshu.com/p/52dee5b08c29)
```
yum -y install git wget
yum -y install bash-completion zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```


* [安装 redis](https://xyzghio.xyz/dbInCentOS/)
```
* yum install -y redis
* 注释 bind 127.0.0.1一行,使其可以被远程客户端访问,
* 将 protected-mode yes 一行更改为 protected-mode no
* 使能后台模式，将 daemonize no 一行更改为 daemonize yes
* 设置密码,requirepass 123456
```

* [安装 mysql](https://xyzghio.xyz/dbInCentOS/)([资源地址](http://repo.mysql.com/))
    * [yum安装软件postfix时报错libmysqlclient.so.18()(64bit)](https://blog.csdn.net/Moniicoo/article/details/86647080)
    * [CentOS7yum安装mysql+需要：libsasl2.so.2()(64bit)](https://blog.csdn.net/qq_38417808/article/details/81291588)
    * yum 安装
    ```
    yum localinstall http://repo.mysql.com/mysql57-community-release-el7-10.noarch.rpm
    yum install -y mysql-community-server # 安装
    ```

    * [mysql 5.7.28 rpm 安装](https://blog.csdn.net/shangyexin/article/details/102720834)
    ```
    wget http://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/mysql-community-common-5.7.28-1.el7.x86_64.rpm
    wget http://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/mysql-community-libs-5.7.28-1.el7.x86_64.rpm
    wget http://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/mysql-community-client-5.7.28-1.el7.x86_64.rpm
    wget http://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/mysql-community-server-5.7.28-1.el7.x86_64.rpm
    wget http://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/mysql-community-devel-5.7.28-1.el7.x86_64.rpm

    # 安装 yum
    rpm -ivh mysql-community-common-5.7.28-1.el7.x86_64.rpm mysql-community-libs-5.7.28-1.el7.x86_64.rpm  mysql-community-client-5.7.28-1.el7.x86_64.rpm mysql-community-server-5.7.28-1.el7.x86_64.rpm mysql-community-devel-5.7.28-1.el7.x86_64.rpm
    ```

    * 修改初始密码和授权
    ```
    cat /var/log/mysqld.log| grep password # 获取密码
    mysql -u root -p # 登录 mysql
    alter user 'root'@'localhost' identified by '123456'; # 修改密码
    systemctl restart mysqld # 重启服务
    mysql -u root -p # 登录
    grant all privileges on `*.*` to 'root'@'%' identified by '123456' with grant option; # 授权
    flush privileges; # 刷新授权
    ```

* [miniconda 安装及操作指南](https://blog.51cto.com/loufeng/2342003)
* [Centos 7 下部署 Redis](https://xyzghio.xyz/dbInCentOS/)


* [安装 Postgresql](https://www.postgresql.org/download/linux/redhat/)
    * [postgresql yum 源](https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7.5-x86_64/) | [postgresql10安装](https://blog.csdn.net/templarzq/article/details/100916016)
    ```
    # 安装依赖组件
    yum install libicu
    yum install libxslt

    # 下载相关安装包
    curl -o postgresql10-10.7-2PGDG.rhel7.x86_64.rpm https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7-x86_64/postgresql10-10.7-2PGDG.rhel7.x86_64.rpm
    curl -o postgresql10-contrib-10.7-2PGDG.rhel7.x86_64.rpm https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7-x86_64/postgresql10-contrib-10.7-2PGDG.rhel7.x86_64.rpm
    curl -o postgresql10-libs-10.7-2PGDG.rhel7.x86_64.rpm https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7-x86_64/postgresql10-libs-10.7-2PGDG.rhel7.x86_64.rpm
    curl -o postgresql10-plpython-10.7-2PGDG.rhel7.x86_64.rpm https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7-x86_64/postgresql10-plpython-10.7-2PGDG.rhel7.x86_64.rpm
    curl -o postgresql10-server-10.7-2PGDG.rhel7.x86_64.rpm https://download.postgresql.org/pub/repos/yum/10/redhat/rhel-7-x86_64/postgresql10-server-10.7-2PGDG.rhel7.x86_64.rpm
    
    # rpm 安装
    rpm -ivh postgresql10-libs-10.7-2PGDG.rhel7.x86_64.rpm        
    rpm -ivh postgresql10-10.7-2PGDG.rhel7.x86_64.rpm        
    rpm -ivh postgresql10-contrib-10.7-2PGDG.rhel7.x86_64.rpm        
    rpm -ivh postgresql10-server-10.7-2PGDG.rhel7.x86_64.rpm      
    rpm -ivh postgresql10-plpython-10.7-2PGDG.rhel7.x86_64.rpm
    
    # 初始化 postgresql
    /usr/pgsql-10/bin/postgresql-10-setup initdb 
    
    # 设置开机启动
    systemctl enable postgresql-10

    # 启动 postgresql
    systemctl start postgresql-10

    # 查询 postgresql 状态
    systemctl status postgresql-10
    
    # 切换 postgres 用户
    su - postgres
    
    # 进入命令行, 创建数据库并修改密码
    psql
    create database agency;
    alter user postgres with password 'GD43j4grrr567';
    \q; # 退出
    
    # 修改配置文件， 把认证 METHOD的ident修改为trust，实现用账户和密码来访问数据库
    vi /var/lib/pgsql/10/data/pg_hba.conf
    IPV4
    host    all             all             0.0.0.0/0               md5

    # 开启远程访问
    vi /var/lib/pgsql/10/data/postgresql.conf 修改监听所有
    listen_address = "*"
    
    # 切换postgres角色到root，并重启
    exit
    systemctl restart postgresql-10
    
    # 导入sql文件新建表
    psql -h 127.0.0.1 -U postgres -d agency -f table.sql -a # 输入密码


    ```