# server-deployment

//linux
//安装mysql
//1.0 安装目录  /usr/bin/mysql

//2.0 下载 wget https://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.24-linux-glibc2.12-x86_64.tar.gz
           如果没有wget 安装wget yum -y install wget
      
//2.1 官网下载 https://downloads.mysql.com/archives/community/

//3.0 安装 解压 tar xzvf mysql-5.7.24-linux-glibc2.12-x86_64.tar.gz
           mv mysql-5.7.24-linux-glibc2.12-x86_64 /usr/local/mysql
           mkdir /usr/local/mysql/data
           //开放权限
           chown -R mysql:mysql /usr/local/mysql
           chmod -R 755 /usr/local/mysql
           //添加用户
           
//4.0 初始化 ./mysqld --initialize --user=mysql --datadir=/usr/local/mysql/data --basedir=/usr/local/mysql
//5.0 配置my.cnf vi /etc/my.cnf
           [mysqld]
           datadir=/usr/local/mysql/data
           port=3306
           sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
           symbolic-links=0
           max_connections=600
           innodb_file_per_table=1
           lower_case_table_names=1
           character_set_server=utf8
           
//6.0 开启服务
           ln -s /usr/local/mysql/support-files/mysql.server /etc/init.d/mysql
           ln -s /usr/local/mysql/bin/mysql /usr/bin/mysql
      
//7.0 开启远程连接
           use mysql;
           update user set user.Host='%' where user.User='root';
           flush privileges;
//安装aphace 
//

//安装php
      查看当前 PHP 版本
            php -v
            查看当前 PHP 相关的安装包，删除之
            yum list installed | grep php
            yum remove php
            yum remove php-*
            
      更换 RPM 源
            #Centos 5.X：
            rpm -Uvh http://mirror.webtatic.com/yum/el5/latest.rpm

            #CentOs 6.x：
            rpm -Uvh http://mirror.webtatic.com/yum/el6/latest.rpm

            #CentOs 7.X：
            rpm -Uvh https://mirror.webtatic.com/yum/el7/epel-release.rpm
            rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
            
      安装新版本 PHP
            php 7.0/7.1/7.2 分别表示为 70w/71w/72w
 
            目前（2018-5-4）

            CentOs 6.x 的 RPM 源中最高只有 7.1

            CentOs 7.x 的 RPM 源中有 7.2
            
            yum install -y php71w php71w-cli php71w-common php71w-devel php71w-embedded php71w-fpm php71w-gd php71w-mbstring 
                           php71w-mysqlnd php71w-opcache php71w-pdo php71w-xml php71w-ldap php71w-mcrypt






